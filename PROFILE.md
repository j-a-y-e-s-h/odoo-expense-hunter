# Odoo Expense Hunter

> ⚡ **Lightning-fast bookmarklet to search Odoo expense logs by person, status & keyword**

A powerful browser bookmarklet for Odoo that instantly searches expense entries and their complete activity logs. Filter by employee, status, and keywords to find approvals, rejections, and comments in seconds.

## ✨ Features

- 🔍 **Quick Search** — Find expenses by employee or status instantly
- 📝 **Log Tracking** — See complete activity history (approvals, rejections, comments)
- 🎯 **Smart Filters** — Person + Status + Keyword search
- 📊 **Status Badges** — Visual indicators (Posted, Rejected, Log)
- ⚡ **Zero Dependencies** — Pure JavaScript, works in any browser
- 🔐 **Read-Only** — Safe inspection tool, no data modification

## 🚀 Quick Start

1. **Copy** the bookmarklet code from `bookmarklet-v2.html`
2. **Create** a new bookmark in your browser
3. **Paste** the JavaScript code as the URL
4. **Go to** your Odoo Expense page
5. **Click** the bookmark → search instantly!

🎬 [View screenshots & detailed guide →](SCREENSHOTS.md)

## 📖 Full Documentation

- [README.md](README.md) — Complete feature guide & usage instructions
- [SCREENSHOTS.md](SCREENSHOTS.md) — Visual walkthrough with examples

## 🛠 Tech Stack

- **Pure JavaScript** — No build tools or dependencies
- **Odoo RPC** — Uses native Odoo API (`/web/dataset/call_kw`)
- **Browser APIs** — Fetch, DOM manipulation, LocalStorage
- **Tailored for** — Chrome, Edge, Firefox, Safari 17+

## 📋 What It Searches

| Model | Purpose |
|-------|---------|
| `expense.usage.line` | Expense records (person, status, amount) |
| `mail.message` | Activity logs & status change history |

## 🎯 Use Cases

- **Find rejected expenses** → Select employee + Status: Rejected
- **Track approvals** → Watch status changes in activity logs
- **Audit trail** → See who approved/rejected each expense
- **Budget review** → Search expenses by keyword (e.g., "travel", "supplies")

## 📊 Status Reference

| Status | Meaning |
|--------|---------|
| **Draft** | Not yet submitted |
| **Submitted** | Awaiting approval |
| **Posted** | Approved & recorded |
| **Rejected** | Needs revisions |

## 🔐 Security

- ✅ **Read-only** — No modifications to data
- ✅ **Browser-based** — No external servers
- ✅ **Uses Odoo auth** — Works with existing user permissions
- ✅ **No storage** — No data logged or tracked

## 🤝 Contributing

Found a bug? Have a suggestion? [Open an issue!](../../issues)

Want to improve the bookmarklet? [Submit a pull request!](../../pulls)

## 📄 License

MIT License — Feel free to use, modify, and share

## 🎓 Learn More

- [Odoo Documentation](https://www.odoo.com/documentation/)
- [JavaScript Bookmarklets](https://en.wikipedia.org/wiki/Bookmarklet)
- [Odoo RPC API](https://www.odoo.com/documentation/13.0/reference/external_api.html)

---

**Made with ❤️ for finance teams & Odoo enthusiasts**  
⭐ If this helps you, please star the repo!
