# 📸 Screenshots & Demos

## 1. Bookmarklet in Action

### Main Panel - Filter View
![Expense Log Search Panel](docs/screenshot-1-panel.png)

The bookmarklet appears as a clean right-side panel on your Odoo Expense page. Shows:
- **Blue header** with title "Expense Log Search" + close button (✕)
- **Person dropdown** — auto-populated with 15+ employees from your system
- **Status dropdown** — All Status / Draft / Submitted / Posted / Rejected
- **Keyword input** — optional text search in activity logs
- **Search button** — blue CTA to execute the search
- **Info area** — shows status ("Ready. Select filters and press Search")

---

### Full Integration - Live Odoo Page
![Full Odoo Expense Page with Panel](docs/screenshot-2-integration.png)

Shows the bookmarklet integrated seamlessly into Odoo's Expense Usage page:
- Left side: Standard Odoo expense table (dates, employees, expense types, amounts)
- Right side: Expense Log Search panel with dropdown open
- **Person list visible:** Ashok Patel, Abhay Iathiya, Ajay Dhoriya, Arpit Patel, Ashok Patel, Aaif Raza, Dharmik Savani, Dhaval Patel, Dhruvin Rakholiya, Kavy Parmar, Mahendra Jamanesha, Pinank Timbadiya, Rashik Mavani, Tulsi Makwana, Vishal Kalathiya

---

## 2. Status Filter Options

### Status Dropdown Expanded
```
All Status          (selected - shows all)
Draft              (expenses not yet submitted)
Submitted          (pending approval)
Posted             (approved & posted)
Rejected           (rejected, needs revision)
```

---

## 3. Example Search Results

### Search Scenario: Find all rejected expenses from Ashok Patel

**Filters applied:**
- Person: `Ashok Patel`
- Status: `Rejected`
- Keyword: *(empty)*

**Expected results:**
- Multiple log entries showing rejection reasons
- Each entry displays:
  - ✓ Employee name (Ashok Patel)
  - 🔴 Status badge (Rejected)
  - Date/Time of log entry
  - Message preview (e.g., "Budget limit exceeded")
  - Clickable link to open full record

---

## How to Add Screenshots

To include screenshots in this repo:

1. **Take screenshots** of the bookmarklet in action (as shown above)
2. **Create directories:**
   ```
   mkdir docs
   ```
3. **Save screenshots as:**
   - `docs/screenshot-1-panel.png` — Panel view
   - `docs/screenshot-2-integration.png` — Full page integration
   - `docs/screenshot-3-results.png` — Results example (optional)

4. **Commit:**
   ```
   git add docs/
   git commit -m "Add screenshots for documentation"
   git push
   ```

---

## UI Elements Visualization

### Color Scheme
| Element | Color | Hex |
|---------|-------|-----|
| Header & Button | Blue | `#2d6cdf` |
| Posted Badge | Green | `#2d6d1a` (bg: `#eef6e8`) |
| Rejected Badge | Red | `#a32d2d` (bg: `#fce8e8`) |
| Log Badge | Amber | `#8a6000` (bg: `#fef5e0`) |
| Text | Dark Gray | `#222` |
| Border | Light Gray | `#eee` |

---

## Mobile Responsiveness

⚠️ **Currently NOT mobile-optimized:**
- Fixed 480px width panel
- Best on desktop (1024px+ screens)
- May overlap on tablets
- Not tested on mobile

---

## Browser Compatibility

✅ **Tested & Working:**
- Chrome 120+
- Edge 120+
- Firefox 121+
- Safari 17+

✅ **Features:**
- JavaScript ES6+ (no transpilation needed)
- Fetch API
- DOM manipulation
- Sessionless (uses browser cookies)

---

## Live Demo

**URL:** https://yourodoo.instance.com/odoo/expense-usage  
**Steps:**
1. Click the `Expense Log Search` bookmark
2. Panel appears on right
3. Select Person: `Ashok Patel`
4. Select Status: `Rejected`
5. Click **Search**
6. See all log entries in seconds

---

## Video Demo

*Coming soon: Short GIF showing the search workflow*

