# Make It Count Goodies – Order Form

A one-page order form. Customers pick items, fill in their info, and click **Submit Order**; the order is emailed to the baker.

## Editing the menu (Google Sheet)

The menu can live in a Google Sheet, so the baker changes items without touching any code.

**One-time setup**

1. Go to [sheets.new](https://sheets.new), then **File → Import → Upload** and choose `menu-template.csv` from this repo (pick "Replace current sheet").
2. **File → Share → Publish to web**. Choose the menu sheet and **Comma-separated values (.csv)**, click **Publish**, and copy the link.
3. In `index.html`, paste that link into `MENU_SHEET_URL` in the **BAKER SETTINGS** block and push the change.

**Day to day** – just edit the sheet. Changes show on the order form within about 5 minutes (Google refreshes published sheets on its own schedule).

| Column | What to put |
| --- | --- |
| Name | Item name (required) |
| Description | Short description (optional) |
| Dose | e.g. `10mg THC` (optional) |
| Price | Price per unit, e.g. `6` or `$6.00` (required) |
| Unit | e.g. `each`, `4-pack`, `dozen` (blank = each) |
| Sold Out | `yes` to show the item but block ordering; blank otherwise |

Rows with no name or price are skipped, and only people the sheet is shared with can edit it. If the sheet can't be loaded, the form falls back to the backup `MENU` in `index.html`.

## Other settings

Everything else is in the **BAKER SETTINGS** block at the top of `index.html`:

- `BAKER_EMAIL` – where orders are sent
- `SEND_METHOD` – `"formsubmit"` (sent from the page via FormSubmit.co) or `"mailto"` (opens the customer's email app)
- `MENU` – backup menu, one line per item
- `MISSION`, `NOTE_AT_TOP` – the text under the company name

## First-time setup

With `"formsubmit"`, the first order triggers an "Activate Form" email to `BAKER_EMAIL`. Click the link once; every order after that arrives normally.

## Hosting

Any static host works (Netlify Drop, GitHub Pages, etc.). Upload this folder; `index.html` is the page.
