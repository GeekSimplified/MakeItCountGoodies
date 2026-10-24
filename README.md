# Make It Count Goodies – Order Form

A one-page order form. Customers pick items, fill in their info, and click **Submit Order**; the order is emailed to the baker.

## Editing the menu

Open `index.html` and edit the **BAKER SETTINGS** block at the top — nothing else needs touching.

- `BAKER_EMAIL` – where orders are sent
- `MENU` – one line per item (`name`, `desc`, `dose`, `price`, `unit`, optional `soldOut: true`)
- `SEND_METHOD` – `"formsubmit"` (sent from the page via FormSubmit.co) or `"mailto"` (opens the customer's email app)

## First-time setup

With `"formsubmit"`, the first order triggers an "Activate Form" email to `BAKER_EMAIL`. Click the link once; every order after that arrives normally.

## Hosting

Any static host works (Netlify Drop, GitHub Pages, etc.). Upload this folder; `index.html` is the page.
