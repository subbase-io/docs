# SubBase Terminology & Concepts

This document defines canonical terms used in SubBase user guides.
All documentation should use these terms consistently and avoid synonyms
unless explicitly noted.

---

## Platform Overview

SubBase is a construction procurement platform that helps subcontractors manage
purchasing, inventory, invoices, and vendor relationships. The platform supports
both individual companies and enterprise accounts with multiple branches.

---

## Core Roles

### Subcontractor (Buyer)
A construction company or team that uses SubBase to procure materials,
manage inventory, track deliveries, and process invoices. This is the
primary user of the platform.

### Vendor (Supplier)
A company that supplies materials, equipment, or services to subcontractors.
Vendors receive purchase orders and quotes via email or the **Vendor Portal**,
and may submit quotes and confirm orders.

### User
An individual person who logs into SubBase. Users belong to a Company and
have specific roles and permissions that determine what actions they can take.

---

## Organizational Structure

### Account
The top-level organizational unit in SubBase. An Account contains one or
more Companies and enables centralized procurement across multiple branches.

- Used for **Centralized Procurement** where a parent organization needs
  visibility across multiple branch companies.
- Users can belong to multiple companies within the same account.

### Company
A business entity within an Account. Each Company has its own:
- Projects
- Vendors
- Materials database
- Orders, invoices, and inventory
- User permissions and settings

### Branch Company
A subsidiary company within an Account that operates semi-independently
but reports to a centralized parent company for procurement oversight.

### Project
A construction job or site where materials are delivered and work is performed.
Projects are the primary way to organize and track procurement activity.

- Each project has its own cost codes, addresses, and assigned users.
- Orders, invoices, and inventory can be filtered by project.

### Project Group
A collection of related projects, often used to organize work by region,
client, or business unit. Project groups help filter and report on activity
across multiple projects.

### Warehouse
A physical or logical storage location for inventory. Warehouses can be:
- Company-wide (shared across all projects)
- Project-specific (dedicated to a single project)

---

## Material Management

### Material Database (Catalog)
A predefined list of materials that a company uses for ordering, quoting,
and invoice reconciliation. The material database ensures consistency
across all procurement activities.

### Company Material
A specific material in a company's database, including:
- Description
- Unit of measure
- Cost codes
- Vendor pricing (if available)
- Manufacturer information

### Unit of Measure
The standard measurement for ordering and tracking materials (e.g., EA, LF, CY, TON).

### Manufacturer
The company that produces a material. Manufacturers can be tracked separately
from vendors to support specification compliance and reporting.

---

## Procurement Workflow

### Draft Request
An internal request for materials created by a field user or requester.
Draft requests must be reviewed and approved before becoming orders.

- Can be converted to a **Purchase Order** or **Request for Quote**
- Supports multiple vendors for comparison

### Material Request
A formal internal request from field workers for specific materials.
Material requests can be fulfilled via:
- **Purchase Order** (ordering new materials from a vendor)
- **Inventory Request** (drawing from existing warehouse stock)

### Request for Quote (RFQ)
A request sent to one or more vendors asking for pricing on specific materials.
RFQs allow comparing quotes before placing an order.

**RFQ States:**
- **Unreviewed** – RFQ created but not yet reviewed
- **Quote Requested** – Sent to vendor, awaiting quote
- **Quote Received** – Vendor has provided pricing
- **Ordered** – RFQ converted to a purchase order
- **Cancelled** – RFQ no longer needed

### Quote
A vendor's response to an RFQ, containing proposed pricing and terms.
Quotes can be uploaded as PDF files or entered as line item pricing.

- Quotes may have an expiration date
- Quotes can be extracted automatically using AI/OCR

### Purchase Order (PO)
A formal order sent to a vendor requesting materials, equipment, or services
at agreed pricing and quantities.

**PO States:**
- **Draft** – Created but not yet sent to vendor
- **Requested** – Internal request awaiting approval
- **Approved** – Approved internally, ready to send
- **Ordered** – Sent to vendor
- **Confirmed** – Vendor has acknowledged the order
- **Partially Shipped** – Some deliveries have shipped
- **Shipped** – All deliveries have shipped
- **Delivered** – All materials received
- **Cancelled** – Order cancelled

### Order Number
A unique identifier assigned to each purchase order. Order numbers are
sequential within a project and company.

### Line Item (Order Material)
A single material entry on a purchase order, including:
- Description
- Quantity
- Unit price
- Extended cost (quantity × unit price)
- Cost code

---

## Delivery & Fulfillment

### Delivery
A scheduled or completed shipment of materials for a purchase order.
A single order may have multiple deliveries.

**Delivery States:**
- **Unscheduled** – No delivery date set
- **Requested** – Delivery date requested
- **Scheduled** – Delivery date confirmed
- **Shipped** – Materials have left the vendor
- **Delivered** – Materials received at destination

### Delivery Ticket
Documentation (usually a signed receipt or BOL) confirming materials were
received. Delivery tickets can be uploaded and processed automatically.

### Fulfillment
The process of receiving and verifying materials against a purchase order.
Fulfillments track:
- Quantities received
- Receipt dates
- Any discrepancies or issues

### Ship Request
A special type of order for transferring materials between locations
within the same company.

---

## Inventory Management

### Inventory
Materials that have been purchased and are stored in a warehouse.
Inventory is tracked by quantity and value.

### Stock
A specific inventory item in a warehouse, with quantities tracked as:
- **Available** – Ready to be requested
- **Committed** – Reserved for a request but not yet consumed
- **Quality Hold** – Under review or quarantine
- **Rejected** – Removed from usable inventory

### Stock Types
- **Consumable** – Materials used up when consumed (e.g., lumber, concrete)
- **Returnable Asset** – Equipment that is checked out and returned (e.g., tools)

### Inventory Request
A request to draw materials from warehouse inventory rather than ordering
from a vendor.

**Inventory Request States:**
- **Draft** – Request being created
- **Unreviewed** – Submitted, awaiting review
- **Approved** – Request approved
- **Prepare Materials** – Warehouse preparing the order
- **Ready for Pickup** – Materials staged for pickup
- **Delivered** – Materials received
- **Rejected/Cancelled** – Request denied or cancelled

### Inventory Draw Down
The act of allocating materials from existing inventory to a project,
reducing available stock quantities.

### Stock Transaction
A record of any inventory movement (add, consume, transfer, adjust).

### Transfer
Moving inventory from one warehouse to another within the company.

---

## Commitments

### Commitment
A long-term agreement with a vendor that defines expected pricing, quantities,
or spend over time. Orders can be linked to commitments to track progress.

**Commitment States:**
- **Drafted** – Being created
- **Confirmed** – Active and approved
- **Partially Delivered** – Some orders delivered
- **Delivered** – All obligations fulfilled
- **Cancelled** – No longer active

### Commitment Types

#### Material Commitment
An agreement for specific materials at negotiated prices. Tracks:
- Committed quantities and pricing
- Ordered quantities
- Remaining quantities

#### Concrete Commitment
A specialized commitment for concrete pours, including:
- Mix designs
- Pour schedules
- Delivery locations
- Vendor coordination

#### Lot Budget Commitment
A budget-based commitment allocating funds to specific material categories
or item types.

---

## Invoice Processing

### Invoice Inbox
A centralized location where invoices are received (via email or upload)
and processed automatically using AI/OCR extraction.

### Invoice
A request for payment from a vendor. Invoices are matched to purchase orders
and commitments during reconciliation.

**Invoice States:**
- **Unreviewed** – Received but not yet processed
- **Approved** – Verified and ready for payment
- **Rejected** – Invoice disputed or incorrect
- **Posted** – Synced to accounting system (ERP)

### Invoice Reconciliation
The process of matching invoice line items to purchase orders, deliveries,
and commitments to verify accuracy before payment.

### Invoice Material
A line item on an invoice, matched to order materials during reconciliation.

---

## Financial & Accounting

### Cost Code
A project-specific accounting code used to categorize and track spending.
Cost codes typically include:
- **Phase** – Project phase or stage
- **Class** – Category of work or material type
- **Number** – Specific line item identifier

### Tax Code
A tax classification applied to materials or orders for accurate tax calculation.

### Terms and Conditions
Standard contract terms that can be attached to purchase orders as PDF documents.

---

## Vendor Management

### Company Vendor
A vendor relationship specific to a company, including:
- Contact information
- Payment terms
- Default pricing
- Performance history

### Vendor Contact
An individual contact person at a vendor company who receives orders and communications.

### Price Sheet
A document containing vendor pricing for specific materials over a time period.
Price sheets can be:
- Uploaded and matched to the material database automatically
- Linked to specific projects or company-wide
- Set to expire after a certain date

### Vendor Portal
A web interface where vendors can:
- View and respond to purchase orders
- Submit quotes
- Confirm orders
- Upload delivery documentation
- Communicate with buyers

---

## Integrations

### ERP (Enterprise Resource Planning)
External accounting and job cost systems that SubBase connects to, including:
- **Foundation** – Accounting software for construction
- **Sage 300 CRE** – Construction management ERP
- **Viewpoint Vista** – Construction ERP
- **QuickBooks Online (QBO)** – Small business accounting
- **CMIC** – Construction management software
- **Procore** – Construction project management

### PO Sync
Automatically syncing purchase orders between SubBase and an ERP system.
Keeps both systems up-to-date with order status and details.

### Invoice Sync
Automatically syncing approved invoices to an ERP for payment processing.

### Agave
Integration platform used to connect SubBase with various ERP systems.

---

## Workflow & Approvals

### Order Flow
Configurable workflow rules that determine how orders progress through
approval stages. Companies can customize:
- Required approvals by dollar amount
- Automatic routing rules
- State transitions

### Flow State
A customizable status in an order or invoice workflow. Companies can create
custom states beyond the defaults to match their approval processes.

### Assignee
The user responsible for taking action on an order, invoice, or request
at the current workflow stage.

### Watcher
A user who receives notifications about an order or request without being
the primary assignee.

---

## Centralized Procurement

### Centralized Procurement
An enterprise feature allowing a parent company to have visibility and
control over procurement across multiple branch companies.

### Centralized Company
The parent company in a centralized procurement setup that can view
and manage data from all branch companies.

### Branch Company
A subsidiary company whose procurement data flows up to the centralized
parent company.

---

## Notifications & Communication

### Notification
An in-app or email alert about important events like:
- Order status changes
- New invoices received
- Approvals needed
- Delivery updates

### Comment
Internal notes or messages attached to orders, invoices, or other records
for team communication.

---

## Reporting & Analytics

### Order Planning
A feature for planning future material needs and scheduling orders in advance.

### Reports
Analytics and summaries of procurement activity, including:
- Spend by vendor, project, or cost code
- Order status summaries
- Delivery performance
- Invoice aging

---

## AI-Powered Features

### Invoice OCR
Automatic extraction of invoice data (vendor, amounts, line items) from
uploaded PDF documents using AI/OCR technology.

### Quote Extraction
Automatic extraction of pricing from vendor quote documents.

### Material Matching
AI-powered matching of invoice or quote line items to the company material database.

---

## Status & State Language

Use the following state names exactly as written in documentation:

### Order States
- **Draft** – Created but not sent
- **Requested** – Internal request submitted
- **Approved** – Approved internally
- **Ordered** – Sent to vendor
- **Confirmed** – Vendor acknowledged
- **Partially Shipped** – Some deliveries shipped
- **Shipped** – All deliveries shipped
- **Delivered** – All materials received
- **Cancelled** – Order cancelled

### Invoice States
- **Unreviewed** – Awaiting review
- **Approved** – Ready for payment
- **Rejected** – Disputed or incorrect
- **Posted** – Synced to ERP

Avoid introducing alternative state names unless the product explicitly supports them.

---

## Writing Rules for AI-Generated Docs

- Prefer concrete nouns over abstractions (e.g., "Purchase Order" instead of "request")
- Use title case for feature names (e.g., "Material Database" not "material database")
- Do not invent features, workflows, or permissions not in the product
- If a workflow differs by role (Subcontractor vs Vendor), call it out explicitly
- If behavior is unclear, mark it as **TODO** instead of guessing
- Always specify which states or features are configurable vs fixed
- Reference specific screens or navigation paths when describing how to do something
