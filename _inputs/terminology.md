# SubBase Terminology & Concepts

This document defines canonical terms used in SubBase user guides.
All documentation should use these terms consistently and avoid synonyms
unless explicitly noted.

---

## Core Roles

### Subcontractor
A company or team responsible for performing work on a construction project.
Subcontractors use SubBase to procure materials, manage inventory, and work with vendors.

### Vendor
A supplier that provides materials, equipment, or services to subcontractors.
Vendors receive purchase orders and may send invoices.


---

## Procurement Concepts

### Purchase Order (PO)
A formal request sent from a subcontractor to a vendor requesting materials,
equipment, or services at agreed pricing and quantities.

- A PO can be in **Draft** or **Sent** status.
- Sending a PO delivers it to the vendor (typically via email or integration).

### Line Item
An individual material, equipment, or service listed on a purchase order,
including quantity, unit cost, and description.

### Material Database
A predefined list of materials that will be utilized when ordering, quoting, or reconciling invoices

---

## Inventory Concepts

### Inventory
Materials that have already been purchased and are stored in a warehouse,
yard, or on-site location.

### Inventory Draw Down
Allocating materials from existing inventory to a project or task,
instead of issuing a new purchase order to a vendor.

- Used when materials are already on hand.
- Reduces available inventory counts.

### Warehouse
A physical or logical location where inventory is stored.
Inventory may be shared across projects or scoped to a specific project.

---

## Commitments

### Commitment
A long-term or recurring agreement with a vendor that defines expected
spend or volume over time.

Commitments may be tied to specific material categories or services.

#### Commitment Types
- **Rental Commitment** – recurring equipment rentals
- **Formwork Commitment**
- **Concrete Commitment**
- **Post-Tension (PT) Commitment**
- **Rebar Commitment**

---

## Financial & Accounting Concepts

### Cost Code
A project-specific accounting code used to categorize spend.
Cost codes are often required when creating purchase orders or inventory allocations.

### Invoice
A request for payment sent by a vendor after fulfilling a purchase order
or commitment.

### Invoice Reconciliation
The process of matching an invoice to one or more purchase orders,
line items, or inventory draw downs.

---

## Integrations

### ERP (Enterprise Resource Planning)
An external system of record used by construction companies
for accounting and job cost management (e.g., Foundation, Viewpoint).

### PO Sync
Automatically syncing purchase orders between SubBase and an ERP system.

### One-time Import
A bulk import of historical data (such as old purchase orders)
from an external system into SubBase.

---

## Status & State Language

Use the following state names exactly as written:

- **Draft** – created but not yet sent
- **Sent** – delivered to the vendor
- **Approved** – approved internally (if applicable)
- **Canceled** – no longer valid

Avoid introducing alternative state names unless the product supports them.

---

## Writing Rules for AI-Generated Docs

- Prefer concrete nouns over abstractions (e.g., “Purchase Order” instead of “request”)
- Do not invent features, workflows, or permissions
- If a workflow differs by role (Subcontractor vs Vendor), call it out explicitly
- If behavior is unclear, mark it as **TODO** instead of guessing