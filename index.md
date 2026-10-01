# Uniform POS User Manual

> **Documentation status:** Initial curated edition. This manual is grounded in the current application routes, schemas, templates, and seeded permissions. Screenshot checkpoints are included throughout; replace each checkpoint with an annotated application capture as the corresponding workflow is verified in the running system.

## Screenshot convention

Screenshots should be stored under `docs/screenshots/` using the names shown in the checkpoints below. Each capture should show the relevant screen, the active store where applicable, and only safe demonstration data. Do not capture passwords, access tokens, payment credentials, or real customer information.

## Table of Contents

1. [About This POS Manual](#1-about-this-pos-manual)
2. [Getting Started](#2-getting-started)
3. [Starting a Shift](#3-starting-a-shift)
4. [Finding Products](#4-finding-products)
5. [Processing a Standard Sale](#5-processing-a-standard-sale)
6. [M-Pesa Payments](#6-m-pesa-payments)
7. [Managing Orders](#7-managing-orders)
8. [Processing Returns and Refunds](#8-processing-returns-and-refunds)
9. [Managing Customers](#9-managing-customers)
10. [Creating and Managing Special Orders](#10-creating-and-managing-special-orders)
11. [Basic Product and Stock Updates](#11-basic-product-and-stock-updates)
12. [Cashier Reports and Daily Review](#12-cashier-reports-and-daily-review)
13. [Ending a Shift](#13-ending-a-shift)
14. [Manager Overview](#14-manager-overview)
15. [Managing the Product Catalogue](#15-managing-the-product-catalogue)
16. [Bulk Inventory Import](#16-bulk-inventory-import)
17. [Monitoring Stock Levels](#17-monitoring-stock-levels)
18. [Transferring Inventory Between Stores](#18-transferring-inventory-between-stores)
19. [Managing Orders and Invoices](#19-managing-orders-and-invoices)
20. [Managing Returns and Refunds](#20-managing-returns-and-refunds)
21. [Managing Special Orders](#21-managing-special-orders)
22. [Reports and Business Analytics](#22-reports-and-business-analytics)
23. [Employee Performance and Audit History](#23-employee-performance-and-audit-history)
24. [Administrator Overview](#24-administrator-overview)
25. [Managing Stores](#25-managing-stores)
26. [Assigning Employees to Stores](#26-assigning-employees-to-stores)
27. [Managing Employee Roles](#27-managing-employee-roles)
28. [Multi-Store Inventory Administration](#28-multi-store-inventory-administration)
29. [Notifications and System Alerts](#29-notifications-and-system-alerts)
30. [Store Synchronization](#30-store-synchronization)
31. [Payment Status Reference](#31-payment-status-reference)
32. [Special-Order Status Reference](#32-special-order-status-reference)
33. [Return and Refund Status Reference](#33-return-and-refund-status-reference)
34. [Common Errors and Resolutions](#34-common-errors-and-resolutions)
35. [Security and Operational Best Practices](#35-security-and-operational-best-practices)
36. [Glossary](#36-glossary)

---

## 1. About This POS Manual

This manual explains how to operate the Uniform POS system as a cashier, manager, or administrator. It follows the application’s real workflows: sales, payments, orders, returns, special orders, customers, inventory, stores, employees, notifications, reports, and synchronization.

### 1.1 Purpose and audience

- **Cashiers** use the sales, customer, order, return, special-order, inventory-view, and daily-review procedures.
- **Managers** use cashier procedures plus catalogue, bulk inventory, transfers, invoice, refund, special-order oversight, and employee-audit procedures.
- **Administrators** use all procedures, including store configuration, employee assignment, roles, notifications, and synchronization.

### 1.2 User roles and access levels

The seeded roles are `cashier`, `manager`, and `admin`.

- Cashiers can process sales, view orders and inventory, manage customers, process refunds, manage special orders, collect payments, and view scoped reports.
- Managers can also delete orders, generate invoices, import inventory, transfer inventory, and view employee audit information.
- Administrators have all permissions and can manage stores, assignments, roles, notifications, and multi-store operations.

### 1.3 Store-based access and data visibility

Non-admin users work within their assigned store. Administrators can select a store for store-specific operations or review broader data. Product, inventory, order, customer, report, notification, and special-order visibility may therefore depend on the active store scope.

### 1.4 Common terms and status labels

See [Payment Status Reference](#31-payment-status-reference), [Special-Order Status Reference](#32-special-order-status-reference), [Return and Refund Status Reference](#33-return-and-refund-status-reference), and the [Glossary](#36-glossary).

---

## 2. Getting Started

### 2.1 Opening the POS

1. Open the POS address supplied by your system administrator.
2. Confirm that the welcome or login page loads.
3. Select the appropriate store if the login form provides a store selection.

> **Screenshot checkpoint:** `screenshots/02-01-login-screen.png` - Login screen before credentials are entered.

### 2.2 Registering a user

1. Open the registration page.
2. Enter a unique username, email address, and password.
3. Select a store when required.
4. Submit the registration form.
5. Sign in with the new account.

The first registered user is assigned the `admin` role. Later registrations default to `cashier` and must be assigned an appropriate role by an administrator.

### 2.3 Signing in

1. Enter your username and password.
2. Select your assigned store if prompted.
3. Submit the form.
4. Confirm that the Menu screen opens and shows the expected role and store.

> **Screenshot checkpoint:** `screenshots/02-02-menu-with-role-and-store.png` - Menu screen showing the permitted navigation items.

### 2.4 Signing out

1. Open the account or settings control.
2. Choose **Logout**.
3. Confirm that the access cookie is cleared and the login page is shown.

### 2.5 Identifying your assigned store

Open the Menu or account context and verify the username, role, store name, store code, and available permissions before processing store-sensitive work.

### 2.6 Understanding the main menu

The main menu links to the Sales Dashboard, Orders, Special Orders, Inventory, Store Management, Customers, Employees, Notifications, Settings, Reports, and other permitted areas. Items may be hidden when the account lacks the required permission.

### 2.7 Understanding permissions and access-denied messages

If an action returns an authorization error, confirm your role and assigned store with a manager or administrator. Do not attempt to work around a permission boundary.

---

## 3. Starting a Shift

1. Sign in and confirm the assigned store.
2. Open the Dashboard.
3. Review sales, order, customer, and inventory indicators.
4. Open Notifications and review new-order, low-stock, failed-transaction, and customer-registration alerts.
5. Open Inventory and confirm that frequently sold variants have stock.

> **Screenshot checkpoint:** `screenshots/03-01-start-of-shift-dashboard.png` - Dashboard at the beginning of a shift.

---

## 4. Finding Products

### 4.1 Searching the product catalogue

1. Open **Inventory**.
2. Search by product description, type or SKU.
3. Open the product record to inspect its variants.

### 4.2 Filtering by category and product type

Use the category and type filters to narrow the catalogue. Confirm that the selected product is active and belongs to the current store context.

### 4.3 Understanding product variants

Verify the SKU, size, color, price, production cost, active state, and available stock before adding a variant to a sale.

### 4.4 Scanning a barcode or entering a SKU

1. Open the sales scanner.
2. Scan the barcode or enter the SKU.
3. Confirm the returned product and variant details.
4. Add the item to the sale.

> **Screenshot checkpoint:** `screenshots/04-01-product-lookup.png` - Product lookup showing SKU, size, color, price, and stock.

### 4.5 Handling an unknown or unavailable product

If the system reports **Product not found** or **Variant not found**, verify the barcode/SKU, product activation, store assignment, and inventory record. Ask a manager to correct catalogue data when necessary.

---

## 5. Processing a Standard Sale

1. Open the sales screen.
2. Scan products or add them by SKU.
3. Select the correct size and color variant.
4. Adjust quantities.
5. Review subtotal, tax, total, and line totals.
6. Check that stock is sufficient.
7. Add or select the customer when customer details are needed.
8. Select `cash payout`, `mpesa`, `credit card`, or `multiple` as the payment method.
9. Complete the payment process.
10. Confirm the invoice ID and payment reference.
11. Wait for an M-Pesa payment to become confirmed before treating the sale as complete.
12. Verify that the final order status is `confirmed`.

Stock is deducted only after payment is confirmed. A new-order notification is generated when the order is placed.

> **Screenshot checkpoint:** `screenshots/05-01-cart-before-payment.png` - Cart with products, variants, quantities, subtotal, tax, and total.

> **Screenshot checkpoint:** `screenshots/05-02-payment-methods.png` - Payment method selection.

> **Screenshot checkpoint:** `screenshots/05-03-confirmed-sale.png` - Confirmed sale showing invoice ID and payment reference.

### 5.1 Processing multiple payments

1. Choose **Multiple**.
2. Enter each payment amount and method.
3. Complete the cash portion when applicable.
4. Start the M-Pesa portion when applicable.
5. Confirm the order only after the combined payments cover the total.

### 5.2 Handling insufficient stock

Do not reduce the requested quantity to force a checkout without customer approval. Check another variant or store, or ask a manager about replenishment or transfer options.

---

## 6. M-Pesa Payments

1. Select **M-Pesa** at checkout.
2. Enter the customer’s phone number in the accepted format.
3. Send the STK Push.
4. Ask the customer to approve the prompt on their phone.
5. Keep the order open while the payment is `pending`.
6. Poll or refresh the payment status when the interface provides that option.
7. Continue only when the payment is `paid` and the order is `confirmed`.

For paybill/C2B payments, use the supplied order reference such as `ORDER-<id>` or special-order reference such as `SPECIAL-<id>`. Never guess a payment reference.

> **Screenshot checkpoint:** `screenshots/06-01-mpesa-pending.png` - M-Pesa payment waiting for customer approval.

> **Screenshot checkpoint:** `screenshots/06-02-mpesa-confirmed.png` - Confirmed M-Pesa result and receipt/reference.

If the payment fails, check the phone number, customer approval, network availability, and transaction status. Do not create a duplicate payment until the original status is understood.

---

## 7. Managing Orders

1. Open **Orders**.
2. Review the order list for the current store.
3. Open an order to view its items, quantities, prices, payment method, payment status, total, refunds, and balance.
4. Use the invoice ID when discussing the order with a customer or manager.
5. Review return status and returned quantities for each item.

> **Screenshot checkpoint:** `screenshots/07-01-order-list.png` - Orders list with store-scoped records.

> **Screenshot checkpoint:** `screenshots/07-02-order-details.png` - Order details with payment, refund, balance, and item information.

---

## 8. Processing Returns and Refunds

1. Locate the original order.
2. Open the item to be returned.
3. Enter the return reason and quantity.
4. Confirm that the quantity does not exceed the quantity still available for return.
5. Submit the return.
6. Verify the return status, refund amount, new order total, and restored stock.

Returns may be `partial` or `returned`. The `refund_order` permission is required, and non-admin users may process returns only for their assigned store.

> **Screenshot checkpoint:** `screenshots/08-01-return-form.png` - Return reason and quantity before submission.

> **Screenshot checkpoint:** `screenshots/08-02-return-confirmed.png` - Return result showing status, refund, and returned quantity.

---

## 9. Managing Customers

### 9.1 Registering a new customer

1. Open **Customers**.
2. Choose **Add/Register Customer**.
3. Enter the customer’s name and phone number.
4. Submit the form.
5. If the phone number already exists, confirm that the existing customer record is being used.

Customer records are associated with the current store, and registration creates a customer notification.

### 9.2 Viewing and updating customer information

1. Search the customer list.
2. Open the customer record.
3. Confirm the name, phone number, store, and creation date.
4. Apply permitted changes and verify the saved record.

> **Screenshot checkpoint:** `screenshots/09-01-customer-record.png` - Customer list and selected customer record.

---

## 10. Creating and Managing Special Orders

### 10.1 Create a special order

1. Open **Special Orders**.
3. Add each custom item.
4. Record name, description, size, color, quantity, and price.
5. Add notes and confirm the order total.
6. Collect the required deposit.
2. Select or enter the customer.
7. Wait for the deposit payment to become `paid`.
8. Create the special order.
9. Confirm that the order starts as `in_production`.

A special order cannot be created until its referenced deposit is paid.

> **Screenshot checkpoint:** `screenshots/10-01-special-order-items.png` - Custom items, measurements, quantities, and pricing.

> **Screenshot checkpoint:** `screenshots/10-02-special-order-deposit.png` - Deposit payment and deposit status.

### 10.2 Track production and delivery

1. Open the special-order list.
2. Open the order record.
3. Update the status to `in_production`, `ready`, or `delivered` as work progresses.
4. Add notes when the status changes.
5. Collect additional payments when required.
6. Calculate and verify the outstanding balance.
7. Collect the balance and confirm delivery.

> **Screenshot checkpoint:** `screenshots/10-03-special-order-status.png` - Special-order status update with notes.

> **Screenshot checkpoint:** `screenshots/10-04-special-order-complete.png` - Completed order showing payments, balance, and delivery status.

---

## 11. Basic Product and Stock Updates

Users with inventory-update permission can create and update products, variants, categories, images, and stock for their permitted store.

1. Open **Inventory**.
2. Create or open a product.
3. Enter its type, description, category, tax rate, and active state.
4. Add or update variants using SKU, color, size, price, production cost, and stock.
5. Upload supported product images when needed.
6. Save the product.
7. Reopen it and verify the store inventory balance.

### 11.1 Manage categories

1. Open the category controls.
2. Add a category, rename it, or remove it.
3. Confirm that products still have the intended category.

> **Screenshot checkpoint:** `screenshots/11-01-product-editor.png` - Product editor with category and variants.

> **Screenshot checkpoint:** `screenshots/11-02-category-management.png` - Category list and edit controls.

---

## 12. Cashier Reports and Daily Review

1. Open **Reports** or the Dashboard analytics area.
2. Review total sales, units, orders, average order value, and revenue growth.
3. Review top products, category sales, monthly sales, monthly orders, monthly average order value, and monthly profit when available to your role.
4. Apply date, category, and product-type filters.
5. Confirm that the report is scoped to your assigned store.

> **Screenshot checkpoint:** `screenshots/12-01-cashier-report.png` - Store-scoped report with filters and KPI cards.

---

## 13. Ending a Shift

1. Confirm that completed sales are `confirmed`.
2. Review pending or failed M-Pesa payments.
3. Review returns and refunds processed during the shift.
4. Review low-stock and failed-transaction notifications.
5. Report unresolved payment, stock, or order issues to a manager.
6. Sign out.

---

## 14. Manager Overview

Managers perform cashier work and control broader inventory, order, invoice, transfer, refund, special-order, report, and employee-audit workflows. Manager access remains store-scoped unless an administrator grants broader access through the application’s role model.

> **Screenshot checkpoint:** `screenshots/14-01-manager-menu.png` - Manager menu showing manager-only navigation.

---

## 15. Managing the Product Catalogue

1. Open **Inventory**.
2. Add, rename, or remove categories.
3. Create products and variants.
4. Set tax rates, prices, production costs, active state, size, color, and SKU.
5. Upload and remove product images.
6. Review the product using category and type filters.
7. Verify that the store inventory reflects the intended stock.

> **Screenshot checkpoint:** `screenshots/15-01-catalogue-management.png` - Manager catalogue controls.

---

## 16. Bulk Inventory Import

1. Download the product CSV template.
2. Populate category, description, type, SKU, color, size, production cost, price, stock, tax rate, active state, and optional image URLs.
3. Save the file as `.csv`.
4. Open the bulk import control.
5. Select the destination store when required.
6. Upload the file.
7. Review the imported count and message.
8. Open Inventory and verify representative products, variants, images, and store stock.

The importer can create missing categories and products and skips duplicate variants safely. Only CSV files are accepted.

> **Screenshot checkpoint:** `screenshots/16-01-csv-template.png` - Completed safe demonstration CSV.

> **Screenshot checkpoint:** `screenshots/16-02-import-result.png` - Import result and count.

---

## 17. Monitoring Stock Levels

1. Open **Inventory**.
2. Open the low-stock view.
3. Review variants at or below the threshold; the default threshold is 50 units.
4. Filter by store, category, or product type.
5. Review description, SKU, size, color, store, and remaining quantity.
6. Replenish, transfer, or deactivate stock as appropriate.
7. Confirm that the low-stock notification resolves after stock is restored.

> **Screenshot checkpoint:** `screenshots/17-01-low-stock-view.png` - Low-stock list with threshold and filters.

---

## 18. Transferring Inventory Between Stores

1. Open Store Management or the inventory transfer control.
2. Select different source and destination stores.
3. Select an active product variant.
4. Enter a quantity no greater than the source stock.
5. Submit the transfer.
6. Verify that source stock decreased and destination stock increased.
7. Confirm the transfer status is `completed`.

Non-admin users can transfer only from their assigned store.

> **Screenshot checkpoint:** `screenshots/18-01-inventory-transfer.png` - Transfer form before submission.

---

## 19. Managing Orders and Invoices

1. Open Orders.
2. Review orders within the permitted store scope.
3. Open an order and verify its items, payments, refunds, and balance.
4. Delete an order only when authorized and operationally necessary.
5. Generate a tax invoice for an order.
6. Open the invoice list and verify the invoice number and status.

> **Screenshot checkpoint:** `screenshots/19-01-invoice-generation.png` - Order action menu and generated tax invoice.

---

## 20. Managing Returns and Refunds

1. Locate the order and item.
2. Verify the customer’s return reason and quantity.
3. Confirm the return does not exceed the unreturned quantity.
4. Submit the refund.
5. Verify the revised total, refund total, return status, and restored stock.
6. Retain the order and audit information according to store policy.

> **Screenshot checkpoint:** `screenshots/20-01-manager-refund-review.png` - Manager review of a refund result.

---

## 21. Managing Special Orders

1. Open the paginated special-order list.
2. Review customer, items, notes, deposit status, payment history, and store.
3. Update production status and notes.
4. Record additional payments.
5. Verify the outstanding balance.
6. Confirm delivery only after payment and fulfilment requirements are complete.

> **Screenshot checkpoint:** `screenshots/21-01-special-order-queue.png` - Manager special-order queue.

---

## 22. Reports and Business Analytics

1. Open Reports.
2. Select a date range.
3. Filter by category, product type, or store when permitted.
4. Review total sales, total units, total orders, average order value, and revenue growth.
5. Review top products and their variants and stock.
6. Review category sales and monthly sales.
7. Review monthly orders, monthly average order value, and monthly profit.
8. Review customer counts and order counts.
9. Export or record approved management figures according to business policy.

> **Screenshot checkpoint:** `screenshots/22-01-analytics-dashboard.png` - Analytics dashboard with filters and charts.

---

## 23. Employee Performance and Audit History

1. Open **Employees**.
2. Select an employee.
3. Open employee insights.
4. Review joined date, first activity, last activity, total actions, successful actions, denied actions, success rate, action breakdown, and recent actions.
5. Open employee sales for day, month, or year.
6. Review total sales, order count, units sold, average order value, and sale details.

> **Screenshot checkpoint:** `screenshots/23-01-employee-insights.png` - Employee activity and performance view.

---

## 24. Administrator Overview

Administrators have full access, including multi-store selection, store setup, employee assignment, role management, notification management, and synchronization. Confirm the selected store before making any store-specific change.

> **Screenshot checkpoint:** `screenshots/24-01-admin-menu.png` - Administrator menu with full navigation.

---

## 25. Managing Stores

1. Open **Store Management**.
2. View active stores.
3. Choose **Create Store**.
4. Enter a unique name, code, and address.
5. Save the store.
6. Open the store record and verify its details.
7. Update the name, code, or address when required.

Store names and codes must be unique.

> **Screenshot checkpoint:** `screenshots/25-01-store-list.png` - Active store list.

> **Screenshot checkpoint:** `screenshots/25-02-store-editor.png` - Store creation or editing form.

---

## 26. Assigning Employees to Stores

1. Open Employees or Store Management.
2. Select an employee.
3. Select an active store.
4. Save the assignment.
5. Ask the employee to sign in and confirm the new store scope.

> **Screenshot checkpoint:** `screenshots/26-01-employee-store-assignment.png` - Employee assignment control.

---

## 27. Managing Employee Roles

1. Open the employee management area.
2. Select an employee.
3. Choose `cashier`, `manager`, or `admin` according to responsibility.
4. Save the role change.
5. Confirm that the employee sees only the intended navigation and actions.

Use the least powerful role that supports the employee’s duties.

> **Screenshot checkpoint:** `screenshots/27-01-role-management.png` - Employee role assignment.

---

## 28. Multi-Store Inventory Administration

1. Select the target store.
2. View that store’s inventory.
3. Add or update products and variants for the selected store.
4. Upload or remove product images for the selected store.
5. Import bulk inventory into the selected store.
6. Review low-stock inventory by store.
7. Transfer stock between active stores when required.

> **Screenshot checkpoint:** `screenshots/28-01-store-scoped-inventory.png` - Inventory screen with store selector.

---

## 29. Notifications and System Alerts

1. Open Notifications.
2. Review notifications newest first.
3. Open low-stock notifications to inspect product, variant, store, and remaining stock.
4. Review new-order, customer-registration, revenue, average-order-value, failed-transaction, milestone, inactive-product, and system-event notifications when present.
5. Mark an individual notification as read.
6. Mark all visible notifications as read.
7. Delete a notification only when authorized.

> **Screenshot checkpoint:** `screenshots/29-01-notification-centre.png` - Notification list with unread and low-stock examples.

---

## 30. Store Synchronization

1. Confirm that local and central database services are available.
2. Confirm the intended store context and backup/operational window.
3. Run synchronization from the administrator control.
4. Review the result.
5. Verify representative products, orders, inventory, and store records.
6. Report any synchronization failure with the displayed error details.

> **Screenshot checkpoint:** `screenshots/30-01-synchronization-result.png` - Synchronization control and result.

---

## 31. Payment Status Reference

| Status | Meaning |
| --- | --- |
| `pending` | Payment has started but is not confirmed. |
| `paid` | The payment record has been settled successfully. |
| `confirmed` | The order has received enough successful payment to complete checkout. |
| `failed` | The payment attempt did not complete successfully. |

Supported checkout methods include cash payout, M-Pesa, credit card, and multiple payments. Special-order payment flows primarily use M-Pesa and cash payout.

---

## 32. Special-Order Status Reference

| Status | Meaning |
| --- | --- |
| `requested` | The special order has been requested but is not yet in production. |
| `in_production` | The order has a paid deposit and is being prepared. |
| `ready` | The order is ready for collection or delivery. |
| `delivered` | The order has been delivered or completed. |

Deposit statuses include `pending`, `paid`, `failed`, and `waived` where supported by the workflow.

---

## 33. Return and Refund Status Reference

| Status | Meaning |
| --- | --- |
| `none` or `Active` | No quantity has been returned. |
| `partial` | Some, but not all, of the item quantity has been returned. |
| `returned` | The full item quantity has been returned. |

The refund is calculated from returned quantity multiplied by the item price. Returned quantities are added back to stock by the current return workflow.

---

## 34. Common Errors and Resolutions

| Message or condition | Recommended action |
| --- | --- |
| Invalid credentials | Re-enter credentials or ask an administrator to verify the account. |
| User is not assigned to that store | Confirm the employee’s store assignment. |
| Product or variant not found | Verify SKU, activation, and catalogue data. |
| Not enough stock | Reduce quantity only with customer approval, or replenish/transfer stock. |
| Payment failed | Check payment method and transaction state before retrying. |
| Payment still pending | Wait for M-Pesa confirmation and check the payment record. |
| Phone number required for M-Pesa | Enter the customer’s valid phone number. |
| Duplicate store name or code | Choose a unique store name and code. |
| Only CSV files are supported | Upload a `.csv` file based on the product template. |
| Return quantity exceeds available | Enter only the quantity not already returned. |
| Not authorized | Ask a manager or administrator to verify the required permission. |
| Store synchronization failed | Record the error and contact the administrator or system support. |

---

## 35. Security and Operational Best Practices

1. Protect usernames, passwords, tokens, and payment credentials.
2. Never include secrets in screenshots or support tickets.
3. Sign out after completing a shift.
4. Verify M-Pesa confirmation before releasing goods.
5. Confirm SKU, size, color, quantity, and price before checkout.
6. Verify the active store before changing inventory.
7. Review audit records for sensitive actions.
8. Use cashier, manager, and administrator roles appropriately.
9. Avoid duplicate payments when a previous payment is pending.
10. Use demonstration data when training or capturing screenshots.

---

## 36. Glossary

- **SKU:** Stock keeping unit used to identify a product variant.
- **Product variant:** A sellable combination of product, size, color, price, and SKU.
- **Store inventory:** The stock balance of a variant at a specific store.
- **Order:** A standard completed or attempted sale.
- **Special order:** A custom order containing user-entered items and production details.
- **Deposit:** An initial payment collected before a special order is created.
- **Balance:** The amount still owed on a special order or order record.
- **STK Push:** An M-Pesa payment prompt sent to a customer’s phone.
- **C2B payment:** A paybill/business-short-code payment received with a reference.
- **Tax invoice:** An invoice record generated for an order.
- **Refund:** The amount returned for an order item return.
- **Audit log:** A record of an employee action, resource, timestamp, and result.
- **Store scope:** The store boundary that controls what a non-admin user can view or change.
- **Permission:** An individual capability granted through a role.

## Screenshot Curation Checklist

- [ ] Capture login and role/store context.
- [ ] Capture Menu, Dashboard, Orders, Special Orders, Inventory, Customers, Employees, Notifications, Reports, Store Management, and invoice screens.
- [ ] Capture successful and pending payment states.
- [ ] Capture return, refund, low-stock, transfer, import, and synchronization results.
- [ ] Annotate each screenshot with numbered callouts matching the procedure steps.
- [ ] Replace every screenshot checkpoint with a verified capture before publishing the manual.
- [ ] Confirm that screenshots contain no real credentials, tokens, payment secrets, or personal customer data.
