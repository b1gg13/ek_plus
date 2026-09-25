WATER OS — Water Business Management System

A web-based system for managing water orders, deliveries, sales, invoices, payments, trucks, clients and expenses in one platform.

1. Project Goal

Create a simple system that tracks the complete water-delivery process:

Client Registration
        ↓
Admin Verification
        ↓
Water Order
        ↓
Order Approval
        ↓
Truck / Staff Assignment
        ↓
Water Dispatch
        ↓
Delivery
        ↓
Client Approval
        ↓
Sale Approval
        ↓
Invoice
        ↓
Payment
        ↓
Reports

⸻

2. Main Users

Admin

Responsible for:

* Client registration and verification
* Managing orders
* Setting water prices
* Assigning trucks and staff
* Approving sales
* Creating invoices
* Recording payments
* Managing expenses
* Viewing reports

Client

Can:

* Register
* Request water
* View quotations
* Confirm orders
* Track delivery status
* Approve delivery
* Report delivery problems
* View invoices
* Make payments
* View payment history

Driver / Staff

Can:

* View assigned deliveries
* View client location
* Start delivery
* Confirm arrival
* Record quantity delivered
* Upload delivery evidence
* Request client approval
* Complete delivery

⸻

3. Core Modules

Dashboard
│
├── Clients
├── Orders
├── Dispatch
├── Deliveries
├── Trucks
├── Water Sources
├── Sales
├── Invoices
├── Payments
├── Expenses
├── Reports
└── Settings

⸻

4. Client Management

Store:

* Client ID
* Client name
* Phone number
* Email
* KRA PIN
* Address
* Delivery location
* Tank capacity
* Client type
* Credit terms
* Account status

Example:

CLIENT-000001
John Doe
10,000 L Tank
15-Day Credit
Active

⸻

5. Water Orders

Every order receives a unique Order ID.

Example:

WTR-2026-000001

Order information:

* Order ID
* Client
* Quantity
* Water source
* Delivery location
* Price
* Delivery charge
* Total
* Requested date
* Order status
* Assigned truck
* Assigned driver

Order Status

REQUESTED
    ↓
VERIFIED
    ↓
APPROVED
    ↓
DISPATCHED
    ↓
EN ROUTE
    ↓
DELIVERING
    ↓
DELIVERED
    ↓
CLIENT APPROVED
    ↓
SALE APPROVED
    ↓
INVOICED
    ↓
PAID

⸻

6. Pricing

The system should calculate prices based on:

* Quantity
* Water source
* Distance
* Truck capacity
* Delivery location
* Urgency
* Client category
* Contract price

Example:

Water              KES 3,000
Delivery           KES 1,500
Urgency             KES 500
--------------------------------
Total              KES 5,000

⸻

7. Truck Management

Each truck should have:

* Truck ID
* Registration number
* Capacity
* Driver
* Current status
* Insurance expiry
* Inspection expiry
* Maintenance records
* Fuel records

Example:

TRUCK-001
KDA 123A
10,000 L
Available

Truck Status

AVAILABLE
ASSIGNED
LOADING
EN ROUTE
DELIVERING
MAINTENANCE
OUT OF SERVICE

⸻

8. Delivery Management

Record:

* Order ID
* Truck
* Driver
* Dispatch time
* Arrival time
* Quantity loaded
* Quantity delivered
* Delivery location
* GPS coordinates
* Photos
* Client confirmation
* Delivery notes

Proof of Delivery

Client can approve using:

✓ OTP
✓ Signature
✓ Photo
✓ Name
✓ Date & Time

⸻

9. Sales

A completed delivery becomes a sale after verification.

Delivery
   ↓
Quantity Verified
   ↓
Price Verified
   ↓
Sale Approved

Sale information:

* Sale ID
* Order ID
* Client
* Quantity
* Amount
* Payment status
* Invoice status
* Sales date

⸻

10. Invoicing

Invoices should contain:

* Invoice number
* Client
* KRA PIN
* Order ID
* Quantity
* Unit price
* Delivery charge
* Total
* Due date
* Payment status

Example:

INV-2026-000001
Amount:       KES 15,000
Invoice Date: 25/09/2026
Due Date:     10/10/2026
Status:       UNPAID

⸻

11. Payments

Record:

* Payment ID
* Client
* Invoice
* Amount
* Payment method
* Transaction/reference number
* Date
* Payment status

Payment methods:

M-PESA
BANK
CASH
CARD
OTHER

⸻

12. Expenses

Track business expenses such as:

* Fuel
* Truck maintenance
* Water purchases
* Staff payments
* Repairs
* Licences
* Utilities
* Other operating expenses

Expense workflow:

Expense Created
      ↓
Submitted
      ↓
Admin Review
      ↓
Approved / Rejected
      ↓
Paid

⸻

13. Water Sources

Track suppliers or boreholes.

Information:

* Source ID
* Source name
* Location
* Supplier
* Price per litre
* Loading capacity
* Contact
* Availability
* Purchase records

Example:

SOURCE-001
ABC Borehole
KES 0.20 / Litre
Available

⸻

14. Dashboard

The main dashboard should show:

TODAY
Orders             24
Deliveries         18
Litres Sold    120,000 L
Sales          KES 180,000
Paid           KES 140,000
Outstanding     KES 40,000
Expenses        KES 55,000

Also display:

* Pending orders
* Deliveries in progress
* Unpaid invoices
* Overdue accounts
* Available trucks
* Trucks on delivery
* Expenses awaiting approval

⸻

15. Reports

Sales

* Daily sales
* Weekly sales
* Monthly sales
* Sales by client
* Sales by truck
* Sales by location

Water

* Litres purchased
* Litres delivered
* Water losses
* Water source usage

Finance

* Revenue
* Payments
* Outstanding invoices
* Expenses
* Profit/margin reports

Operations

* Deliveries completed
* Failed deliveries
* Truck utilization
* Driver activity
* Average delivery time

⸻

16. User Interface

Use a simple Symbian-inspired interface.

Main Menu

┌─────────────────────────────┐
│ WATER OS                    │
├─────────────────────────────┤
│ 👥 Clients     💧 Orders    │
│ 🚚 Trucks      📍 Dispatch  │
│ 🚰 Deliveries  💰 Sales     │
│ 🧾 Invoices    💳 Payments  │
│ 💸 Expenses    📊 Reports   │
└─────────────────────────────┘

Use:

* Simple icons
* Compact menus
* Coloured status indicators
* Pop-up modals
* Tables/lists
* Clear action buttons

Status Colours

GREEN   = Approved / Paid / Completed
YELLOW  = Pending
ORANGE  = Dispatch / Attention
RED     = Problem / Overdue
BLUE    = Information / Water
GREY    = Archived

⸻

17. Recommended Technology

Frontend

Next.js
TypeScript
Tailwind CSS
Lucide Icons

Backend

FastAPI
Python
Pydantic

Database

PostgreSQL

Use PostgreSQL as the main database because orders, invoices, payments and expenses require reliable transactions.

Additional Services

Redis
Background Workers
Object Storage
M-Pesa API
eTIMS Integration
Maps/GPS
SMS/WhatsApp Notifications

⸻

18. Basic Database Structure

users
clients
orders
order_items
trucks
drivers
deliveries
water_sources
water_purchases
sales
invoices
payments
expenses
expense_approvals
notifications
audit_logs

Main relationship:

CLIENT
   │
   ▼
ORDER
   │
   ▼
DELIVERY
   │
   ├── TRUCK
   ├── DRIVER
   └── CLIENT APPROVAL
          │
          ▼
        SALE
          │
          ▼
       INVOICE
          │
          ▼
       PAYMENT

⸻

19. MVP — Version 1

Build these first:

* [ ]	User login
* [ ]	Client registration
* [ ]	Client verification
* [ ]	Water orders
* [ ]	Pricing
* [ ]	Truck management
* [ ]	Driver assignment
* [ ]	Delivery tracking
* [ ]	Client delivery approval
* [ ]	Sales
* [ ]	Invoices
* [ ]	Payments
* [ ]	Expenses
* [ ]	Basic dashboard
* [ ]	Basic reports
* [ ]	Audit log

⸻

20. Future Features

After the MVP:

* [ ]	M-Pesa integration
* [ ]	eTIMS integration
* [ ]	GPS tracking
* [ ]	Maps
* [ ]	SMS notifications
* [ ]	WhatsApp notifications
* [ ]	Recurring orders
* [ ]	Customer credit limits
* [ ]	Automatic overdue reminders
* [ ]	Route optimization
* [ ]	Driver mobile/PWA application
* [ ]	Offline delivery mode
* [ ]	Automated financial reports
* [ ]	AI-assisted reporting

⸻

21. Project Objective

The final system should allow the business to answer:

Who ordered the water?
        ↓
How much was ordered?
        ↓
Where is it being delivered?
        ↓
Which truck is delivering?
        ↓
Who is the driver?
        ↓
How much water was delivered?
        ↓
Did the client approve it?
        ↓
How much was sold?
        ↓
Was an invoice created?
        ↓
Has the client paid?
        ↓
What did the delivery cost?
        ↓
What was the business margin?

Core principle:

Every transaction should be traceable from client → order → delivery → sale → invoice → payment → financial report.