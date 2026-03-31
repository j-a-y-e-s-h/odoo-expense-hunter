# 🔍 Odoo Expense Log Search Bookmarklet

## Overview

This bookmarklet is a **quick-access search tool** for Odoo expense records that integrates seamlessly into your browser. It searches through expense entries in your Odoo database and retrieves the complete log/activity history for each entry—allowing you to track status changes, approvals, rejections, and all comments in one place.

**Use case:** Finance teams and expense approvers can instantly find expenses by employee, status, or keyword without navigating through multiple Odoo screens.

🎬 **[View Screenshots & Demo →](SCREENSHOTS.md)**

---

## How It Works

### Data Scope 
The bookmarklet searches within two connected Odoo models:
- **`expense.usage.line`** — individual expense entries/line items
- **`mail.message`** — activity logs and status change history attached to expense records

When you search, the tool:
1. Fetches all expense records matching your filters (Person, Status)
2. Then fetches all activity logs (`mail.message`) linked to those records
3. Optionally filters logs by keyword
4. Displays results with a rich preview of each log entry

---

## Features Explained

### 🔽 **Person (Employee) Filter**
- **Auto-populated** dropdown of all employees who have expense entries
- Select an employee to show **only their expenses**
- Loaded from the `expense_advance` field in expense records
- Leave blank to search **all employees**

### 🔽 **Status Filter**
Each expense entry has one of these states:

| Status | Meaning | Color Badge |
|--------|---------|------------|
| **Draft** | Expense created but not yet submitted for approval | (no badge) |
| **Submitted** | Submitted to manager/approver for review | Yellow badge |
| **Posted** | Approved and posted to accounting | Green badge |
| **Rejected** | Rejected by approver; requires corrections | Red badge |

- Select a status to view **only expenses in that state**
- Leave blank to search **all statuses**

### 🔎 **Keyword Search in Logs**
- Optional text filter on log/activity message body
- Searches through comments, status change notes, and all recorded activity
- **Case-insensitive**
- Example: search for "budget" to find logs mentioning budget issues

### 📋 **Log Fetching from mail.message**
The bookmarklet retrieves the complete activity trail:
- **Author** — who made the change or comment
- **Date & Time** — when the activity occurred (in local timezone)
- **Message body** — the action or comment (HTML formatting removed)
- **Linked record** — associates each log back to the original expense
- Returns up to **200 recent log entries** per search

### 🎯 **Badge System**
Each log entry displays a color-coded badge:
- 🟢 **Posted** — log related to posting/approval
- 🔴 **Rejected** — log related to rejection
- 🟡 **Log** — general activity/comment (default)

The badge helps you quickly spot important status changes.

---

## How to Use

### Installation (One-Time Setup)

1. **Copy the bookmarklet code:**
   - Open `bookmarklet-v2.html` in a browser
   - Click the **"📋 Copy Code"** button

2. **Add to your bookmarks:**
   - In Chrome: Press `Ctrl+D` → Bookmark current page OR right-click bookmarks bar → Add page
   - **Label it:** "Expense Log Search" (or any name)

3. **Update the bookmark URL:**
   - Right-click the bookmark → **Edit**
   - Delete the current URL
   - Paste the copied code (`Ctrl+V`) → Save

4. **Done!** The bookmarklet is ready to use.

### Using the Bookmarklet

1. Go to your **Odoo expense page** (any page where expense data is visible)
2. Click the bookmark — a search panel appears on the **right side** of the screen
3. **Set your filters:**
   - `All Persons` → choose an employee (optional)
   - `All Status` → choose Draft / Submitted / Posted / Rejected (optional)
   - `Keyword in logs` → type a word to search in activity messages (optional)
4. Click **"Search"** (or press `Enter`)
5. Results appear instantly with:
   - Author name + status badge + employee name
   - Date & time
   - Preview of the log message
   - Click any result to **open the full expense record in a new tab**

### Example Workflows

**Scenario 1:** Find all rejected expenses from a specific employee
- Person: `Ashok Patel`
- Status: `Rejected`
- Keyword: *(leave blank)*
- Result: All of Ashok's rejected expenses + reasons

**Scenario 2:** Search for expenses with budget concerns
- Person: *(all)*
- Status: *(all)*
- Keyword: `budget`
- Result: Any log mentioning "budget" from any expense

**Scenario 3:** Review all posted (approved) expenses
- Person: *(all)*
- Status: `Posted`
- Keyword: *(leave blank)*
- Result: All approved & posted entries in chronological order

---

## Technical Details

### Data Flow
```
User enters filters
         ↓
Search expense records (expense.usage.line model)
         ↓
Extract expense IDs matching filters
         ↓
Fetch activity logs (mail.message model) for those records
         ↓
Filter logs by keyword (if provided)
         ↓
Display results with rich formatting
```

### API Endpoints
The bookmarklet uses Odoo's native RPC endpoint:
- **Endpoint:** `/web/dataset/call_kw`
- **Method:** POST with JSON-RPC 2.0 format
- **Authentication:** Uses browser session (`credentials: 'include'`)

### Limits
- Fetches up to **2,000 expense records** per search
- Returns up to **200 log entries** per search
- Suitable for small-to-medium deployments

---

## UI Components

| Element | Description |
|---------|-------------|
| **Header** (Blue bar) | Title + Close button (✕) |
| **Filter Row** | Person dropdown, Status dropdown, Keyword input, Search button |
| **Info Row** | Status text (Loading, Ready, Searching, Found X entries) |
| **Results Panel** | Scrollable list of log entries with clickable previews |

**Size:** Fixed right-side panel (480px wide, full screen height)  
**Close:** Click the ✕ button or close the browser tab

---

## Troubleshooting

**"Loading persons..." never finishes**
- Check your Odoo connection (refresh the page)
- Ensure you're logged in to Odoo
- Try the search anyway—it may work without pre-loading employees

**No results appear**
- Verify filters are not too restrictive
- Try searching with all filters blank first
- Check if expense records actually exist in your Odoo instance

**"Error: [message]"**
- Refresh the page and try again
- Check browser console (F12) for detailed error messages
- Verify the bookmarklet code was copied completely (including `javascript:` prefix)

---

## Notes for Administrators

- The bookmarklet reads from the `mail.message` table directly
- Requires **read access** to `expense.usage.line` and `mail.message` models
- No write/modification operations — it's **read-only**
- Works with standard Odoo security permissions (existing user roles apply)

---

## Version History

| Version | Date | Changes |
|---------|------|---------|
| **v2.0** | Current | Added Person filter, Status filter, keyword search, badge system, improved UI |
| **v1.0** | — | Initial bookmarklet |

---

## Support

If you encounter issues or need modifications:
- Check that the bookmarklet code wasn't truncated during copy
- Verify the prefix is `javascript:` (not `https://`)
- Test in an incognito/private window to rule out browser cache issues
- Contact your Odoo administrator if logs are missing or inaccessible
