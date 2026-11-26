# Changelog

Release notes for every version from 1.0 on are on the
[releases page](https://github.com/jackthereaper2006/parallax-releases/releases) and are
collected here. Version numbers follow [VERSIONING.md](VERSIONING.md).

---

## 1.14 — 26 November 2026

Parallax 1.14.0 lets you sell a received special order straight onto a bill, and gives Owner drawing its own button.

### New
- **Sell a received special order.** On **Orders ▸ Receive Orders**, a customer's order that has been received shows **Sell on invoice**. It opens the Sale Invoice already filled: the order's customer, each product at the quantity received, at today's sale price (change anything as usual). Complete the sale as normal.
  - The order then shows **Sold on bill …** (click it to open the bill), and the Sell button goes away.
  - An order can be sold only once, only to its own customer. Deleting that bill makes the order sellable again.
  - The advance taken with the order is already a credit on the customer's account, so it shows in Prev Balance.
  - A received order that has been sold can't be taken back; delete the bill first.
- **Owner drawing has its own button.** **Expenses ▸ ↩ Owner drawing**: pick where the money came from (a branch till, a bank or owner cash), enter the amount and press **Pay**. No branch, type or category to choose.
  - Drawings are no longer offered in the normal expense form and no longer mixed into the expense list. They have their own **Owner drawings** pill.

### Before you update
- One small database change (a new column for the order's bill). A backup of HQ was taken just before release. HQ updates itself; then use **Settings ▸ Application ▸ Force update all machines**.

---

## 1.13.1 — 26 November 2026

Parallax 1.13.1 makes the web version (Parallax in a browser) work for orders, stock counts and printing reports.

### Fixed
- **Orders work in the browser.** Order Board, New Order, Special Order, Receive Orders and the Order Ledger used to open empty on the web. They now load and work the same as on the desktop.
- **Stock Count works in the browser.** Opening a count, entering what was found and reviewing the difference all work on the web.
- **Data Integrity works in the browser.**
- **Printing reports from the browser.** Pressing Print on a report (ledgers, Trial Balance, Profit & Loss, salary sheet, contracts, stock reports and the rest) did nothing on the web. It now opens the same A4 page as the desktop in a new tab; **Print** and **Save PDF** use the browser's print dialog (choose "Save as PDF" as the printer).
- Printing a draft bill from the browser now says plainly that bills print from the desktop app.

### Before you update
- No database changes, but take a backup on HQ first as always. HQ updates itself; then use **Settings ▸ Application ▸ Force update all machines**.

---

## 1.13 — 23 November 2026

Parallax 1.13 adds employment contracts to HR and makes branch floats simpler.

### New
- **Employment contracts.** HR ▸ Contracts: enter the employee's details (name, father's name, CNIC, phone, address, emergency contact) and the job (title, location, start date, salary or wages, hours, probation, notice, duties). Print the contract on one A4 page, have the employee sign or put a thumb impression with a witness, then press **Mark signed** to keep it on record.
- Saving a contract adds a new person to Employees, or updates an existing employee. A salary change on a contract counts from the contract date.
- A signed contract is locked. A raise or a new job is made as a **new version**; once it is signed, the old one is kept as an old version. A contract made by mistake can be voided with a reason.
- Each employee has a **Contract** button, and the Contracts page shows how many are waiting to be signed and how many staff have no signed contract.

### Changed
- **Simpler branch floats.** Staff see one Expenses page. Spending up to what is left in their branch's float needs no approval. A bigger expense is asked for first; once approved, it is paid from that branch's till.
- Only an owner tops a float up.
- Approvals, Monthly Bills and Floats show only to people who approve expenses.
- The "daily expenses from the float" and "post without approval" switches are gone from Business Rules.

### Before you update
- **One new table** (the contracts). HQ makes its own safety copy before it opens the database with 1.13, but take a backup on HQ first as always. HQ updates itself; then use **Settings ▸ Application ▸ Force update all machines**.

## 1.12 — 23 November 2026

Parallax 1.12 brings an Expenses module with branch floats, and special orders with receiving at the store.

### New
- **Expenses** is its own module now, with four pages: Expenses, Monthly Bills, Floats and Approvals.
- **Branch floats.** Each branch can be given a fixed float for its spending. Staff pay expenses from the float and an owner approves them; the till tops the float back up only by what was approved.
- **Monthly bills.** Set up electricity, gas, internet and rent once. Each month's payment is entered against its bill, with the bill number, and compared with the usual amount.
- **Ask before spending.** Repairs above a set amount are asked for and approved before the money is spent.
- **Special orders.** Take a custom order for a customer with an advance payment.
- **Receiving at the store.** Sent orders show at the receiving branch, where staff count what arrived and receive it.

### Changed
- Accounts ▸ Expenses has moved to the new Expenses module.
- Sending an order no longer moves stock; the stock moves when the store receives it.

## 1.11 — 22 November 2026

Parallax 1.11 makes every screen easier to read and closes the gaps found by a 25-point security checklist.

### Easier to read
- **Darker text.** Hint text, amber warnings, purple accents and the sidebar labels now stand out clearly from the background. The brand purple is a shade deeper.
- **Field edges you can see.** Text boxes, search boxes and outline buttons have a visible border.
- **Keyboard focus.** Tabbing through a screen now shows a clear ring around the field you are on.
- **No tiny text.** Nothing is smaller than 11px. Labels and table headings are written in normal case instead of small spaced capitals. Status badges (PAID, VOID, …) keep their capitals.
- The sidebar is a little wider so its labels fit.

### Security
- **Every PIN sign-in is logged**, right or wrong; **Settings ▸ Business Rules** lists the last 50. The owner and admins get a popup for a sign-in on a computer that person has never used (quiet for the first 7 days), a PIN lock, or 10 wrong PINs on one computer within 15 minutes.
- HQ checks a customer or supplier before saving it: a blank or very long name, a negative credit limit, or an opening balance that is not a number is refused with a message.
- A database error stays on HQ's log; a till or browser sees a plain sentence instead.
- An old PIN-change route that skipped the PIN rule has been removed.
- Updated react-router and fast-uri for known security problems.

### Before you update
- **One new table** (the sign-in log). HQ makes its own safety copy before it opens the database with 1.11, but take a backup on HQ first as always. HQ updates itself; then use **Settings ▸ Application ▸ Force update all machines**.

## 1.10.1 — 21 November 2026

Parallax 1.10.1 fixes a bill number that could be given out twice, and a handful of small things on prints and screens.

### Fixed
- **Bill numbers are never given out twice.** Deleting the newest bill let the next sale take the same number. A deleted bill's number now stays used.
- A printed bill's time is when the bill was made, not when it was last edited.
- The supplier payment voucher says **Printed by** for the person printing it (it used to say "Paid by").
- The voucher no longer says "Advance" next to a balance of 0.
- Costing Setup's change log shows local time, and its rates refresh after a month-end review is approved.
- Return of bill shows each line's real stock instead of 0 and OUT.
- The PIN prompt reads "Confirm it's you to continue", the idle lock says "1 idle minute", and the Job Register shows weights as Kgs throughout.

### Before you update
- No database changes, but take a backup on HQ first as always. HQ updates itself; then use **Settings ▸ Application ▸ Force update all machines**.

## 1.10 — 19 November 2026

Parallax 1.10 brings a contractor hub, tidies the production screens, and lets an order be taken back a step or deleted.

### New
- **Contractor hub.** A board of factories first: what each one holds, how many days it has been out, how much came back from closed jobs, and what we still owe them. Each job sent out has its own page, and each factory a holding statement. Recording a return takes you back to its job.
- **Orders: take a step back.** On the Order Board an order can go back one step: take back a send (its transfer is voided, the stock returns to the factory shelf and the store is told), untick made, undo a confirm, or reopen a rejected or cancelled order.
- **Orders: delete.** The owner or an admin can delete an order that has not moved stock, with a reason. Its number is not reused.
- **3D Print** warns before saving when the factory shelf does not hold the sheet or ink the job takes.
- **Salary Run** warns when the pay date is in the future.

### Changed
- **Record Production is retired for new work.** New jobs are recorded on Production Run, Tape Converting, 3D Print, Cut Sheets or Contractor Work. Jobs already recorded on it still open.
- Production pages no longer carry their own Back buttons; the Back arrow in the top bar does it.
- The Job Register shows every unfinished job, however many there are, and drops status buttons that could no longer do anything. Finish stays.
- The production Overview links to the contractor ledger and no longer has a Refresh button (it refreshes itself).
- Costing Setup tabs are in a clearer order; the Rate Calculator links to the shaft drawing.
- Wages and increment history name the job each line was earned on, and open it.
- The tape cost line under each size now lists every part of the cost, so it adds up.
- Production approvals show the production site when none was picked.

### Fixed
- The Job Register could leave out jobs past the newest 200, so its In Progress count was too low.
- Price Update history and the drafts list showed times five hours behind.
- The Cut Sheets hint said every kilo carries over even when kilos were recorded as lost.

### Before you update
- No database changes, but take a backup on HQ first as always. HQ updates itself; then use **Settings ▸ Application ▸ Force update all machines**.

---

## 1.9 — 19 November 2026

Parallax 1.9 makes contractor work easier to read, adds an Order Ledger, and fixes an approval that could be marked approved without posting.

### New
- **Orders ▸ Order Ledger.** Every order by day, week or month, with its lines shown inline and totals for the whole period.
- **Contractor Ledger, rebuilt.** One row per job sent out, with its part returns inside it. Three tabs: Jobs, Factories (one card per factory: sent, came back, waste, still there) and Account (the factory's bills and payments with a running balance).
- **A check against the books.** The top of the Contractor Ledger compares its total with Goods at Contractor in the accounts. Any job holding value that the page cannot list is named.

### Changed
- **Only the supplying factory's manager confirms an order**, and never their own order. The owner and admin still can. The Order Board says why Confirm is not offered.
- Each order stage has its own colour on the board.
- **Recording a return from a contractor:** no error is shown before anything is typed, and no figures appear until you say whether more is still coming. A line at the top shows what is with the factory, what this return used, and what stays there. Shorter help text.
- Reverse is no longer on every Contractor Ledger row. It is on the job's own page.

### Fixed
- **A second part return waiting for approval on the same contractor job** could read Approved while nothing was posted. It now posts onto what is still at the factory, and an approval that cannot post stays waiting with the reason.

### Before you update
- No database changes, but take a backup on HQ first as always. HQ updates itself; then use **Settings ▸ Application ▸ Force update all machines**.

---

## 1.8 — 19 November 2026

Parallax 1.8 adds Orders: a sale point asks the factory for stock, and the factory confirms, makes and sends it.

### New
- **Orders ▸ New Order.** A store lists what it needs and places the order. It appears on the factory's Order Board straight away, and the factory gets a popup.
- **Orders ▸ Order Board.** Every order in five columns: Waiting, Confirmed, In production, Made, Sent. The board refreshes every 10 seconds.
- **Confirm or reject.** The factory can change the quantity on each line before confirming, or set a line to 0 to leave it out. A rejected order needs a reason. The store can cancel its own order while it is still waiting.
- **Job sheet.** Print job sheet gives an A4 sheet for the machine and labour team, with a tick box for each line and signature lines.
- **Made and Send.** Tick an order as made, then send it to the store that ordered it or to another one. Sending is an ordinary stock transfer, so it cannot send more than the factory shelf holds. The store gets a popup when its order is sent.
- An order on its own moves no stock and changes no money. Production is still recorded on its own screens.
- New permissions on Settings ▸ Users: view, request, fulfil, send. Operators can do everything except send.

### Before you update
- **This update adds two database tables.** Take a backup on HQ first. HQ updates itself; then use **Settings ▸ Application ▸ Force update all machines**.

---

## 1.7 — 16 November 2026

Parallax 1.7 makes every return name the bill it came from, and tightens security across sign-in, tills and printing.

### New
- **Return of bill on Sale Invoice.** Set Type to Return and type the bill number. The bill's customer and everything still left to return on it come in; keep only what came back and save. A return can take back no more than the bill sold, less what earlier returns already took, at no more than the bill's price.
- **A return with no bill needs the owner.** Only the owner, signed in, can ring a return without naming its bill.
- **A bill whose total does not match its lines is flagged** for the owner to review. It is still saved.

### Changed
- **Security.** Tighter checks on sign-in, PINs, tills, user changes, settings and printed pages. A user whose role, PIN or access is changed signs in again.
- A till that cannot reach HQ no longer takes returns; it still takes cash sales paid in full.
- The Windows installer runs Windows' own tools by their full path, and the backup it makes before erasing data now includes everything needed to open it.

### Fixed
- A refused save on Sale Invoice now shows as an error instead of with the saved tick.

### Before you update
- No database changes, but take a backup on HQ first as always. Tell the counter staff: from now on a return needs its bill number, and a return without a bill needs the owner. HQ updates itself; then use **Settings ▸ Application ▸ Force update all machines**.

---

## 1.6 — 13 November 2026

Parallax 1.6 stops one bad tape job from setting a product's cost, and warns you before you price off an odd cost.

### Changed
- **Damaged pieces are shared across the whole job.** When pieces come off the machine damaged, their cost now spreads over every good piece in the job, by width × length. Before, it landed only on the few good pieces of the same size, so 5 damaged out of 7 could make the other 2 cost three or four times their real cost. The job's total cost is the same; only who carries it changed.
- **A made product's cost on Products is the average of the stock on the shelf**, not the cost of the last job. One unusual job can no longer swing it.

### New
- **"odd cost, check PO-…" on Products.** If stock still on the shelf came from a tape job where one size cost more than 25% away from that job's normal rate, the product says so under its cost, and the job number opens it. Check that job before setting a price from that cost.

### Before you update
- Take a database backup first. On its first start the update resets the cost of every made product to the average of its stock on the shelf, and keeps the old figures. HQ updates itself from 1.5.1, then use **Settings ▸ Application ▸ Force update all machines**.

---

## 1.5.1 — 11 November 2026

Parallax 1.5.1 makes updates safe on Linux computers, including a Linux HQ.

### Fixed
- **A Linux HQ updates itself cleanly.** When an update was installed, the old copy could keep running beside the new one, so the HQ service kept restarting. A later update could also leave the program file missing. The new file now replaces the old one in a single step, and an HQ run as a service restarts once on the new version.
- **Restarting Parallax on Linux restarts it.** Actions that restart the app (changing the connection, restoring a backup, leaving sandbox mode) could close Parallax on Linux instead of opening it again.
- Windows tills are not affected.

### Before you update
- No database changes. A Linux HQ already on 1.5.0 must be updated by hand this once, because its updater is the old one; from 1.5.1 on it updates itself. Then use **Settings ▸ Application ▸ Force update all machines**.

---

## 1.5 — 2 November 2026

Parallax 1.5 adds a product-by-product sales and profit report, shows what each customer still owes and for how long, finds bills by their remarks, and makes the Dashboard and Sales List much faster.

### New
- **Reports ▸ Products.** Every product sold in any period, with quantity sold and returned, sales, cost, profit, margin and bills. Search it, sort it by sales, profit, margin or quantity, and print it.
- **Unpaid tab on the customer ledger.** Lists what the customer still owes, oldest first, with the amount still owed and the days since each entry. Payments clear the oldest entry first, so the total always matches the ledger balance. Pick an As of date to see an earlier position, and print it.
- **Oldest Unpaid on the customer ledger.** A new card at the top shows how old the customer's oldest unpaid entry is.
- **Remarks on the Sales List.** A new Remarks column, and the search box now finds a bill by its remarks.

### Changed
- **Sales List search looks through every bill.** While the dates are on today, a search covers all dates and says so. Pick a date range to search inside it.
- **Reports has two groups** in the menu: Sales & profit, and Stock.

### Fixed
- **The Dashboard and Sales List no longer stall.** Each refresh was taking about a second as bills built up. It now takes a small fraction of that.
- **The Sales List reaches older bills.** A past date range used to show only the most recent 200 bills.

### Before you update
- This version changes the database. Make a fresh backup of HQ first.
- Update HQ first, then use **Settings ▸ Application ▸ Force update all machines**. The new report and the Unpaid tab need HQ to be on 1.5.

---

## 1.4 — 31 October 2026

Parallax 1.4 fixes how wages are charged on packet jobs and corrects the jobs already recorded, brings the logo back on Linux, gives the screen lock more time, and makes the PIN screens match the login screen.

### Fixed
- **Wages on packet jobs are charged per packet.** A family worked in kilos that makes packets was charging wages on the weight of the packets. 300 packets at Rs 20 now cost 300 × 20, whatever they weigh. Crew labour, factory overhead and the increment still run per kilo.
- **Jobs already recorded are corrected automatically.** The first time HQ opens this version, it finds every job charged this way and corrects its wages, the cost of its stock, and any bill that already sold that stock. It makes a backup first and runs once.
- **The Parallax logo is back on Linux.** The taskbar showed a blank placeholder after 1.2.

### Changed
- **The screen locks after 15 minutes of no use**, up from 5. The time can still be changed on Settings ▸ Business Rules.
- **The lock screen and the PIN prompt have been redesigned** to match the login screen.
- **The wages register and Families now name the unit**, such as "300 packets".

### Security
- Updated a network component that could carry saved credentials across a redirect.

### Before you update
- This version corrects figures in the database. Make a fresh backup of HQ first.
- Update HQ first, then use **Settings ▸ Application ▸ Force update all machines**. Tills keep locking at 5 minutes until HQ has updated.

---

## 1.3 — 29 October 2026

Parallax 1.3 adds Cut Sheets: record a sheet cut from one size into another, like 12x18 into 9x12.

### New
- **Production ▸ Cut Sheets.** Pick the sheet that was cut, how many kg, the sheet it became, and the kg that came out. The stock moves across at the same cost. No labour or overhead is added, because the sheet already carried them when it was made.
- **Kg out fills itself in.** Halving 12x18 into 9x12 keeps every kilo. For a cut that does not come out even, such as 12x18 into 8x10, it fills in the share of the sheet the pieces use. Change it if you weighed less.
- **Odd cuts are flagged, not refused.** A cut that does not come out even, more kg out than the cut can give, or two sheets whose names do not look like the same material still records, and the job is marked for a second look with a sentence saying why.
- **It works for every sheet stocked in kg whose name has a size** (12x18, 9x12, 10*15, and the X-ray sizes), at the factory and at the shops. Any kg lost in the cut is spread over the sheets that came out.
- A cut waits in **Production ▸ Approvals** like every other production entry, and the owner can reverse it like any other job.

### Before you update
- No database changes. Make a fresh backup of HQ first anyway.
- Update HQ first, then use **Settings ▸ Application ▸ Force update all machines**.

---

## 1.2 — 22 October 2026

Parallax 1.2 runs on a newer engine, gives each computer an A4 printer, and fixes the Beta switch on tills.

### New
- **An A4 printer for each computer.** Settings, the *Printers (this computer)* card, *A4 printer (invoices, reports)*. Once it is chosen, every A4 invoice and every report prints straight to it on A4 paper, without the print dialog.

### Changed
- **The engine Parallax runs on is updated** to a current, supported version, with the security fixes that brings. Nothing on the screens is meant to change.
- **Windows no longer tells Parallax which printer is the default, or whether a printer is switched off.** Settings no longer marks the default printer on a Windows computer. Before a receipt prints, Parallax still checks a printer shared from another computer, and says so if that computer is off.

### Fixed
- **Switching a till to Beta said "Unauthorized".** The owner can now switch a till between Stable and Beta from Settings.

### Before you update
- No database changes. Make a fresh backup of HQ first anyway.
- Update HQ first, then use **Settings ▸ Application ▸ Force update all machines**.
- **After updating, choose the A4 printer on every computer that prints A4 invoices or reports.** Without it, the print dialog opens, and an A4 page can come out tiny or cut off on the right when a different printer is picked in it.

---

## 1.1 — 22 October 2026

Parallax 1.1 tightens who can do what on a till, and locks a till that is left alone.

### New
- **The till locks itself after 5 minutes with nobody using it.** Whoever was signed in unlocks it with their PIN, and anything half-typed is still there. The owner can change the time, or turn it off, in **Settings ▸ Business Rules**.
- **Lock now, Switch user and Change my PIN** are in the menu under your name, top right. Switching user puts an open bill on hold first, so it is not lost.
- **The PIN is asked again** before a saved bill is edited or deleted, and before Profit, Break-even, Comparison, Profit & Loss or the Balance Sheet is opened. It is not asked again for the next 5 minutes. The owner can turn this off in **Settings ▸ Business Rules**.
- **Deleting a bill needs a reason**, which is kept in the bill's history.

### Changed
- **Sign-ins last 12 hours**, so everyone signs in again each morning.
- **New PINs must be harder to guess.** The owner's PIN is 6 to 8 digits and everyone else's 4 to 8, and easy ones (1111, 1234, the shop's phone number) are refused. PINs already in use keep working until they are changed.
- **Only the owner can enter or change a sale, payment, expense or income on a day that has already been closed.**
- **Importing customers and stock from Excel is for the owner only.** Only the file picked with the Browse button is read. A file over 20 MB or 100,000 rows is refused, and a damaged file gives a message instead of an error.
- **Staff without HR access no longer see pay.** HR screens need HR permission, and Costing Setup hides each person's wage from anyone without it.
- **Who deleted, approved or changed something is taken from who is signed in,** never from what a screen sends.
- **Before a new version starts for the first time, Parallax copies the database,** and does not start if it cannot. The last three copies are kept next to the database.

### Before you update
- No database changes. Make a fresh backup of HQ first anyway.
- Update HQ first, then use **Settings ▸ Application ▸ Force update all machines** straight away: until a till has updated, editing or deleting a saved bill on it is refused.
- Tell everyone they will need their PIN more often from today.

---

## 1.0.2 — 19 October 2026

Parallax 1.0.2 fixes receipts printed from a Linux computer.

### Fixed
- **Receipts printed from a Linux computer come out full size.** Bills sent to a thermal receipt printer from a Linux machine printed very small, or full size with the right side cut off. They now print the same as from a Windows till, and the paper is cut straight after the last line. Windows tills are not affected.

### Before you update
- No database changes, and nothing to do beforehand. Update HQ first, then use **Settings ▸ Application ▸ Force update all machines**.

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
