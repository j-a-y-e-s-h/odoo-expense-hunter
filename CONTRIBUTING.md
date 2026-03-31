# Contributing to Odoo Expense Hunter

Thank you for considering contributing to Odoo Expense Hunter! 🎉

## How to Contribute

### 1. Report a Bug
If you find a bug, please [open an issue](../../issues/new) with:
- **Title:** Brief description of the bug
- **Description:** What you expected vs. what happened
- **Steps to reproduce:** How to trigger the bug
- **Screenshots/Logs:** If applicable
- **Odoo version:** Your Odoo instance version

### 2. Suggest a Feature
Want to see a new feature? [Open an issue](../../issues/new) with:
- **Title:** Feature idea
- **Description:** What problem does it solve?
- **Use case:** How would you use it?
- **Alternatives:** What else did you try?

### 3. Submit Code Changes

#### Setup
1. Fork the repo
2. Clone your fork:
   ```bash
   git clone https://github.com/YOUR_USERNAME/odoo-expense-hunter.git
   cd odoo-expense-hunter
   ```
3. Create a branch:
   ```bash
   git checkout -b feature/your-feature-name
   ```

#### Making Changes
1. Edit `bookmarklet-v2.html`
2. Test in your Odoo instance (click the bookmark)
3. Verify no console errors (F12 → Console)
4. Commit with descriptive message:
   ```bash
   git commit -m "Add feature: xyz - description"
   ```

#### Submitting a PR
1. Push your branch:
   ```bash
   git push origin feature/your-feature-name
   ```
2. Open a Pull Request with:
   - Clear description of changes
   - Reference any related issues (#123)
   - Screenshots if UI changes
   - Testing steps

## Code Style

- **JavaScript:** Keep it clean and readable
- **Comments:** Add comments for complex logic
- **CSS:** Keep styles organized in the `s.textContent` string
- **No external dependencies:** Use native APIs only

## Testing Checklist

Before submitting a PR, test:
- ✅ Works in Chrome, Edge, Firefox, Safari
- ✅ No console errors
- ✅ All filters work (Person, Status, Keyword)
- ✅ Search returns expected results
- ✅ Click links open correct records
- ✅ Close button works
- ✅ Works on both narrow and wide screens

## Documentation

If you add a feature, please update:
- [README.md](README.md) — Add to Features section
- [SCREENSHOTS.md](SCREENSHOTS.md) — Add visual example
- Code comments — Explain complex parts

## Questions?

- Open an [issue](../../issues) to discuss
- Check [SCREENSHOTS.md](SCREENSHOTS.md) for usage examples
- Review [README.md](README.md) for technical details

---

**Thanks for making Odoo Expense Hunter better!** 🚀
