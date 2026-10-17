# Changelog

Release notes for every version from 1.0 on are on the
[releases page](https://github.com/jackthereaper2006/parallax-releases/releases) and are
collected here. Version numbers follow [VERSIONING.md](VERSIONING.md).

---

## 1.0.1 — 17 October 2026

Parallax 1.0.1 works and looks exactly like 1.0. Only the program's internal notes were tidied, so it is easier to look after.

### Before you update
- No database changes, and nothing to do beforehand. Update HQ first, then use **Settings ▸ Application ▸ Force update all machines**.

---

## 1.0 — 15 October 2026

Parallax 1.0 is the same app as 0.5.113, under new version numbers and with its owner's name on it.

### New
- **Version numbers start again at 1.0.** A small fix is now 1.0.1, something new is 1.1, and a large redesign is 2.0. The login screen and Settings show the short form, for example "Parallax 1.0".

### Changed
- **Parallax is owned by Muhammad Waqas Butt**, and BXC is licensed to use it. The Windows installer shows the licence before it installs, and Settings ▸ Application shows the copyright.
- The installers no longer carry the program in readable form, or any of the business's own figures.
- A few example hints inside empty boxes no longer show real names.

### Before you update
- No database changes, and nothing to do beforehand. Update HQ first, then use **Settings ▸ Application ▸ Force update all machines**.

---

## Before 1.0: the development line (0.1.0 to 0.5.113)

Parallax was built and put into daily use over 0.1.0 to 0.5.113, with more than 150 builds in
seven months. Those numbers came before the current rules, so they do not say how big each
change was. Below is a summary of what each period added.

### October 2026 (0.5.101 to 0.5.113)

- **Inventory ▸ Price Update.** When a material's cost goes up, see every product it goes into
  and raise their sale prices in one step. Can be undone.
- **Production ▸ Factory Overview.** What the factory made, used, wasted and sent out over any
  day, week, month, quarter or year.
- **Printed reports** fit A4 portrait without splitting words. Wide lists put the second line
  of detail under the name instead of switching to landscape.
- **Held bills** are shared by every till at a branch: hold on one, resume on another.
- **HR:** a printable salary sheet; pay from a named cash drawer; loans taken back in their own
  box on the salary run; a salary paid late is costed in the month it was for.
- **Supplier Payment** prints a payment voucher. Inactive products can no longer be put on a bill.
- **Production:** figures shown in headed panels on every screen; families choose their
  production line; "Show details" opens a waiting approval on its own screen.
- **One search** everywhere: words in any order, best match first.
- **Reports ▸ Profit** agrees with the Profit & Loss statement, and each card lists what it is
  made of.
- A screen that fails now shows an error card for that page only. The rest of the app keeps
  working.
- Purchasing renamed **Suppliers**.

### September 2026 (0.5.67 to 0.5.100)

- **Accounts ▸ Day Book.** Everything that happened on a day across the whole app, with a
  month history. Printable.
- **Approvals.** Purchases and all production entries can wait for an owner or admin to approve
  them before they touch stock or the books.
- **Costing rebuilt:** factory overhead, machine depreciation, crew labour per line, the
  production increment and wages are all now part of what a product costs.
- **Purchase returns** against the original bill.
- **3D print line** with its own job screen and setup.
- **Contractor work:** goods sent to and received from outside factories, combined per factory
  and product, with a ledger for each factory. A purchase can be sent straight to a factory.
- **Undo within 30 days** for bills, payments and production jobs, including a factory receipt
  on its own.
- **New navigation:** a module rail, grouped pages and Ctrl K search.
- **Each branch numbers its own bills and expenses.**
- **Stock count** lists only that location's stock, in rack order, with refresh and recheck.
- **Tape converting:** extra pieces recovered from waste, and damaged pieces.
- **HR:** salary or wages per person; the wages and increment funds paid from HR.
- **Bill history:** who made each bill and every change since, also printed on the bill.
- A phone layout for the browser version.
- HQ moved to Linux.

### August 2026 (0.5.29 to 0.5.66)

- **Linux support**, built and published alongside Windows.
- **Cheque clearing** for cheques issued and received.
- **Weight-based production** for thermal paper and PET sheet.
- **Settings ▸ Business Rules:** the owner decides, for example, whether stock may go negative.
- **Discounts** have their own accounts on both sales and purchases.
- **Stock transfers** as numbered documents with several products, plus a transfer ledger.
- **Employee ledger** and **employee loans**.
- **Tape costing** on one page, using measured timings instead of typed rates.
- Customers and suppliers share one screen design; every document number opens its document.
- Bank reconciliation by period.

### July 2026 (0.1.30 to 0.5.28)

- **Tills over the internet** as well as the shop network, switching automatically when one
  path fails.
- **Force update** for every machine from HQ.
- **Locations** can be added and renamed in Settings.
- **One A4 report design** across every screen.
- **Physical stock count** with blind counting.
- **Product ledger**: full in and out history per product.
- HQ's thermal printer shared with the whole shop.
- Reminders and configurable pop-up notifications.

### March to June 2026 (0.1.0 to 0.1.29)

- Sale invoice, customers, ledgers and customer tiers.
- Users, PIN login, roles and permissions; first-run setup wizard.
- Purchases, supplier payments, expenses, other income.
- Double-entry accounts with P&L, balance sheet and trial balance; FIFO stock costing.
- Daily closing per branch.
- Dispatch of sold goods.
- Thermal and A4 printing.
- HQ and till network; tills keep selling when HQ is out of reach.
- Automatic updates.
- Tape jumbo-roll converting.
- Import from the previous system.
