VAPECORE POS

MASTER PROJECT SPECIFICATION (MPS)

Document ID: MPS-VCP-001
Version: 1.0.0
Status: Project Baseline
System Classification: Enterprise Retail Operating System
Platform: Web Application
Deployment: Cloud-Based
Architecture: Integrated Modular Monolith
Primary Currency: Indonesian Rupiah (IDR)
Default Timezone: Asia/Jakarta
Primary Language: Bahasa Indonesia

---

1. PROJECT DEFINITION

1.1 Project Overview

VAPECORE POS adalah sistem Enterprise Retail Operating System yang dirancang untuk mengelola, mengintegrasikan, mengawasi, dan mengendalikan seluruh aktivitas operasional perusahaan retail vape store melalui satu platform terpusat.

Sistem mengintegrasikan aktivitas penjualan, pengelolaan produk, persediaan, gudang, distribusi, keuangan, sumber daya manusia, audit internal, procurement, pengelolaan cabang, dan business intelligence.

VAPECORE POS bukan sekadar aplikasi kasir. Sistem ini merupakan infrastruktur digital operasional perusahaan.

1.2 Primary Objectives

1. Menyatukan seluruh data perusahaan dalam satu sumber data terpusat.
2. Menghilangkan duplikasi pekerjaan dan pencatatan.
3. Memperbaiki koordinasi antar-divisi.
4. Meningkatkan akurasi transaksi dan persediaan.
5. Membangun pengendalian keuangan yang dapat direkonsiliasi.
6. Meningkatkan transparansi dan akuntabilitas setiap aktivitas.
7. Menerapkan otorisasi berdasarkan struktur organisasi.
8. Menyediakan monitoring kinerja perusahaan secara real-time.
9. Mengurangi human error dan risiko penyalahgunaan kewenangan.
10. Menyediakan infrastruktur yang dapat dikembangkan seiring pertumbuhan perusahaan.

1.3 Design Principles

Seluruh implementasi wajib mengikuti prinsip berikut:

- Centralized data management.
- Single source of truth.
- Role-based access control.
- Least privilege access.
- Transaction integrity.
- Immutable financial and inventory history.
- Separation of duties.
- Approval-based critical operations.
- Auditability by design.
- Scalable infrastructure.
- API-first integration.
- Security by design.

---

2. SYSTEM SCOPE

Sistem terdiri dari 15 domain utama.

1. Executive Command Center.
2. Point of Sale.
3. Product Management.
4. Inventory Management.
5. Stock Control, Tracking & Cycle Count.
6. Warehouse Management.
7. Distribution & Transfer Management.
8. Finance Management.
9. Human Resource Management.
10. Internal Audit Management.
11. Procurement & Supplier Management.
12. Branch Management.
13. Approval & Workflow Management.
14. Business Intelligence & Reporting.
15. System Administration & Security.

Setiap domain harus mempunyai tanggung jawab bisnis, hak akses, validasi, dan dokumentasi yang jelas.

3. ORGANIZATIONAL ARCHITECTURE

3.1 Organization Hierarchy

Struktur organisasi sistem:

Owner / Board
→ Executive Management
→ Central Management
→ Department Heads
→ Area Supervisors
→ Store Managers
→ Store Employees

Struktur tersebut dapat dikonfigurasi sesuai struktur organisasi aktual.

3.2 Department Structure

A. Executive Management

- Pengawasan keseluruhan perusahaan.
- Persetujuan keputusan strategis.
- Konsolidasi performa bisnis.
- Pengawasan keuangan dan risiko.
- Monitoring performa seluruh divisi.

B. Finance

- Financial reporting.
- Cash reconciliation.
- Expense management.
- Payment settlement.
- Accounts payable.
- Accounts receivable.
- Financial closing.
- Profit and loss reporting.

C. Human Resources

- Employee database.
- Recruitment records.
- Attendance.
- Shift management.
- Payroll preparation.
- Leave management.
- Employee performance.
- Disciplinary administration.

D. Internal Audit

- Operational audit.
- Financial audit.
- Inventory audit.
- Transaction audit.
- Compliance monitoring.
- Audit findings.
- Corrective action monitoring.

Internal Audit harus memiliki independensi dalam pemeriksaan dan tidak boleh mengubah transaksi yang sedang diperiksa.

E. Stock Control, Tracking & Cycle Count (SCT)

- Stock monitoring.
- Cycle counting.
- Stock discrepancy.
- Stock reconciliation.
- Stock movement tracking.
- Stock adjustment verification.
- Inventory integrity.

F. Procurement

- Supplier management.
- Purchase requisition.
- Purchase order.
- Supplier invoice.
- Receiving verification.
- Procurement reporting.

G. Store Operations

- Daily sales.
- Cashier operations.
- Shift opening.
- Shift closing.
- Stock receiving.
- Store inventory.
- Operational checklist.
- Customer transaction controls.

---

4. FUNCTIONAL REQUIREMENTS

4.1 Executive Command Center

Tujuan: menyediakan satu pusat pengawasan perusahaan.

Fitur wajib:

- Consolidated revenue.
- Gross profit.
- Net profit reporting.
- Transaction volume.
- Branch performance.
- Financial position.
- Inventory valuation.
- Stock discrepancy.
- Expense monitoring.
- Department performance.
- Pending approvals.
- Operational alerts.
- Audit findings.
- Management reporting.

Dashboard harus mendukung:

- Filter tanggal.
- Filter cabang.
- Filter area.
- Filter divisi.
- Perbandingan periode.
- Export PDF dan spreadsheet.
- Drill-down ke data sumber.

Angka dashboard harus berasal dari transaksi dan laporan yang dapat ditelusuri.

4.2 Point of Sale (POS)

Fitur wajib:

Product Checkout

- Product search.
- Barcode scanning.
- SKU lookup.
- Product categorization.
- Shopping cart.
- Quantity control.
- Price validation.
- Discount authorization.
- Tax configuration.
- Payment processing.
- Receipt generation.

Transaction Management

- Unique transaction number.
- Cash transaction.
- QRIS payment integration.
- Debit and credit payment integration.
- Bank transfer.
- Split payment.
- Refund.
- Reversal.
- Void with authorization.
- Transaction history.

Cashier Management

- Cashier login.
- Register assignment.
- Shift opening.
- Opening cash.
- Cash movement.
- Shift closing.
- Expected cash calculation.
- Physical cash count.
- Cash variance reporting.

POS Security

- Cashier cannot permanently delete completed transactions.
- Discount above configured thresholds requires approval.
- Refund requires authorization.
- Price changes require permission.
- Every sensitive action must be logged.
- Completed transactions must retain their original details.

Regulatory Controls

- Age verification according to applicable law.
- Restricted-product eligibility.
- Sales restriction configuration.
- Mandatory verification before eligible checkout.
- Block transactions when required checks fail.

4.3 Product Management

Master product fields:

- Product ID.
- SKU.
- Barcode.
- Product name.
- Brand.
- Category.
- Subcategory.
- Description.
- Unit of measurement.
- Purchase cost.
- Selling price.
- Minimum stock.
- Maximum stock.
- Active/inactive status.
- Product eligibility classification.
- Created by.
- Updated by.
- Created timestamp.

Product categories must be configurable.

4.4 Inventory Management

Fitur:

- Stock balance.
- Stock in.
- Stock out.
- Stock adjustment.
- Damaged stock.
- Returned stock.
- Reserved stock.
- Available stock.
- Minimum stock alert.
- Maximum stock monitoring.
- Stock valuation.
- Stock movement history.

Stock calculation:

Available Stock = On-hand Stock - Reserved Stock

Stock balance merupakan projection dari stock movement ledger, bukan sumber histori independen.

Setiap perubahan stok harus mempunyai:

- Product reference.
- Branch/warehouse reference.
- Movement type.
- Quantity delta.
- Reference document.
- Actor.
- Timestamp.
- Reason.

4.5 SCT — Stock Control, Tracking & Cycle Count

SCT merupakan domain pengawasan persediaan.

Fitur:

- Cycle count scheduling.
- Blind stock count.
- Physical stock input.
- System stock comparison.
- Variance calculation.
- Discrepancy investigation.
- Adjustment request.
- Adjustment approval.
- Stock loss reporting.
- Stock accuracy KPI.

Selisih stok tidak boleh langsung dihapus atau disesuaikan tanpa proses investigasi dan otorisasi sesuai matriks kewenangan.

4.6 Warehouse Management

Fitur:

- Central warehouse.
- Warehouse locations.
- Goods receiving.
- Put-away records.
- Stock location tracking.
- Picking.
- Packing.
- Dispatch.
- Goods receipt confirmation.
- Damaged goods records.
- Warehouse stock reports.

4.7 Distribution & Transfer

Workflow transfer:

1. Outlet mengajukan permintaan barang.
2. Supervisor melakukan pemeriksaan.
3. SCT memverifikasi kebutuhan dan ketersediaan.
4. Pihak berwenang memberikan persetujuan.
5. Warehouse melakukan picking.
6. Barang dikirim.
7. Outlet menerima barang.
8. Kuantitas aktual diverifikasi.
9. Stock ledger diperbarui.
10. Transfer ditutup.

Status:

- Draft.
- Submitted.
- Under Review.
- Approved.
- Picking.
- Dispatched.
- Partially Received.
- Received.
- Rejected.
- Cancelled.

4.8 Finance Management

Fitur:

- Cash management.
- Cash reconciliation.
- Revenue monitoring.
- Expense management.
- Petty cash.
- Payment settlement.
- Accounts payable.
- Accounts receivable.
- Financial journal.
- General ledger.
- Profit and loss.
- Cash flow.
- Financial closing.

Sistem keuangan harus menggunakan double-entry accounting untuk pencatatan akuntansi yang relevan.

Setiap jurnal wajib mempunyai:

- Journal number.
- Transaction date.
- Account.
- Debit.
- Credit.
- Source reference.
- Created by.
- Approval status.

Total debit harus sama dengan total kredit pada setiap jurnal yang diposting.

4.9 Human Resource Management

Fitur:

- Employee master data.
- Employee number.
- Department.
- Position.
- Branch assignment.
- Employment status.
- Attendance.
- Shift scheduling.
- Late attendance calculation.
- Leave management.
- Overtime records.
- Payroll preparation.
- Performance evaluation.
- Disciplinary records.
- Employee document management.

Attendance calculation harus mengikuti jadwal kerja yang ditetapkan HR dan konfigurasi waktu istirahat.

Payroll harus dapat dikonfigurasi berdasarkan kebijakan perusahaan dan peraturan ketenagakerjaan yang berlaku.

4.10 Internal Audit

Fitur:

- Audit planning.
- Audit checklist.
- Audit assignment.
- Transaction examination.
- Cash examination.
- Stock examination.
- Employee activity examination.
- Audit evidence.
- Audit findings.
- Risk classification.
- Corrective action.
- Follow-up audit.
- Audit closure.

Risk classification:

- Low.
- Medium.
- High.
- Critical.

Audit records harus memiliki jejak perubahan dan bukti pemeriksaan.

4.11 Procurement & Supplier Management

Fitur:

- Supplier master data.
- Supplier documents.
- Purchase requisition.
- Purchase order.
- Price comparison.
- Purchase approval.
- Goods receipt.
- Invoice verification.
- Supplier payment status.
- Supplier performance.

Purchase Order tidak otomatis meningkatkan stok. Stok bertambah setelah penerimaan barang diverifikasi.

4.12 Branch Management

Fitur:

- Branch master data.
- Branch code.
- Store manager assignment.
- Employee assignment.
- Operating schedule.
- Store opening checklist.
- Store closing checklist.
- Daily sales target.
- Branch KPI.
- Operational incident.
- Branch comparison.

4.13 Approval & Workflow Engine

Approval harus dapat dikonfigurasi berdasarkan:

- Jenis aktivitas.
- Nilai transaksi.
- Jabatan pemohon.
- Cabang.
- Divisi.
- Tingkat risiko.

Jenis approval:

- Discount.
- Refund.
- Void.
- Stock adjustment.
- Stock transfer.
- Purchase order.
- Expense.
- Cash variance.
- Employee administration.

Workflow harus mendukung:

- Sequential approval.
- Multi-level approval.
- Rejection.
- Resubmission.
- Delegation dengan batas kewenangan.
- Escalation.
- Approval history.

Pemohon tidak boleh menyetujui permohonannya sendiri apabila kebijakan separation of duties melarangnya.

4.14 Business Intelligence

Laporan:

- Daily sales.
- Monthly sales.
- Annual sales.
- Gross profit.
- Net profit.
- Product performance.
- Branch performance.
- Employee performance.
- Stock turnover.
- Inventory aging.
- Stock discrepancy.
- Expense ratio.
- Cash variance.
- Supplier performance.

4.15 System Administration

Fitur:

- User management.
- Role management.
- Permission management.
- Branch access.
- Department access.
- Authentication settings.
- Session management.
- Login history.
- Audit logs.
- System configuration.
- Notification settings.
- Backup monitoring.

---

5. USER ACCESS CONTROL

Sistem menggunakan Role-Based Access Control (RBAC) dengan tambahan organization scope dan branch scope.

Role awal:

1. Super Administrator.
2. Owner.
3. Director.
4. General Manager.
5. Finance Manager.
6. Finance Staff.
7. HR Manager.
8. HR Staff.
9. Internal Auditor.
10. SCT Manager.
11. SCT Staff.
12. Warehouse Manager.
13. Procurement Staff.
14. Area Supervisor.
15. Store Manager.
16. Cashier.
17. Store Staff.

Hak akses tidak ditentukan hanya berdasarkan nama jabatan. Setiap role mempunyai permission yang dapat dikonfigurasi.

Permission categories:

- View.
- Create.
- Update.
- Submit.
- Approve.
- Reject.
- Export.
- Reverse.
- Close.
- Administer.

Akses harus diperiksa di backend, bukan hanya dengan menyembunyikan menu frontend.

---

6. DATABASE ARCHITECTURE

Database utama: PostgreSQL.

6.1 Core Tables

Organization:

- organizations
- branches
- warehouses
- warehouse_locations

Identity:

- users
- roles
- permissions
- user_roles
- role_permissions
- user_branch_access
- sessions

HR:

- employees
- departments
- positions
- shifts
- attendance
- leave_requests
- payroll_periods

Catalog:

- products
- product_categories
- product_barcodes
- product_prices
- suppliers

POS:

- sales
- sale_items
- payments
- refunds
- refund_items
- cash_sessions
- cash_movements

Inventory:

- stock_balances
- stock_movements
- stock_reservations
- cycle_counts
- cycle_count_items
- stock_adjustments

Warehouse:

- purchase_orders
- purchase_order_items
- goods_receipts
- goods_receipt_items
- stock_transfers
- stock_transfer_items

Finance:

- chart_of_accounts
- journal_entries
- journal_lines
- expenses
- expense_categories
- settlements
- bank_reconciliations

Audit:

- audit_plans
- audit_assignments
- audit_findings
- audit_evidence
- corrective_actions
- audit_logs

Workflow:

- approval_requests
- approval_steps
- approval_events
- notifications

Reporting:

- report_snapshots
- daily_branch_metrics
- monthly_branch_metrics

6.2 Database Rules

1. Gunakan UUID sebagai primary identifier untuk entitas utama.
2. Gunakan NUMERIC untuk seluruh nominal uang.
3. Gunakan foreign key untuk menjaga referential integrity.
4. Gunakan unique constraints untuk SKU dan nomor transaksi sesuai scope.
5. Gunakan database transactions untuk operasi multi-tabel.
6. Gunakan indexes untuk query operasional.
7. Gunakan soft deactivation untuk master data tertentu.
8. Jangan menghapus histori transaksi yang sudah diposting.
9. Gunakan UTC untuk timestamp penyimpanan.
10. Tampilkan waktu berdasarkan timezone organisasi.

6.3 Data Isolation

Setiap query harus membatasi data berdasarkan organization_id dan kewenangan cabang.

Row-Level Security PostgreSQL digunakan sebagai lapisan pertahanan tambahan.

---

7. APPLICATION ARCHITECTURE

7.1 Technology Stack

Frontend:

- Next.js.
- React.
- TypeScript.
- Tailwind CSS.
- Component-based UI.

Backend:

- NestJS.
- TypeScript.
- REST API.
- OpenAPI documentation.
- WebSocket untuk notifikasi real-time.

Database:

- PostgreSQL.

Cache & Queue:

- Redis.

ORM:

- Prisma atau TypeORM, dipilih dan dikunci sebelum implementasi produksi.

Infrastructure:

- Docker.
- Cloud hosting.
- Managed PostgreSQL.
- Object storage.
- Centralized logging.
- Monitoring and alerting.

7.2 Architecture Pattern

Gunakan modular monolith dengan domain boundaries yang tegas.

Domain modules tidak boleh mengakses database domain lain secara sembarangan.

Integrasi internal dilakukan melalui service contracts, application services, dan domain events.

Distributed services hanya dipertimbangkan ketika kebutuhan beban, independensi deployment, atau skala tim benar-benar memerlukannya.

7.3 Application Layers

1. Presentation Layer.
2. API Controller Layer.
3. Application Service Layer.
4. Domain Layer.
5. Infrastructure Layer.
6. Persistence Layer.

Business rules tidak boleh hanya ditempatkan di frontend.

---

8. UI/UX DESIGN SYSTEM

8.1 Visual Identity

Product name: VAPECORE POS.

Design direction:

- Enterprise.
- Minimalist.
- Professional.
- Data-centric.
- Operationally efficient.

Color system:

- Background: Graphite Black.
- Surface: Dark Charcoal.
- Primary accent: Emerald Green.
- Warning: Amber.
- Danger: Red.
- Neutral: Gray.

Typography:

- Inter atau DM Sans.

8.2 Main Layout

Desktop:

- Permanent sidebar.
- Top navigation.
- Main content.
- Contextual action panel.
- Notification center.

Tablet:

- Collapsible sidebar.
- Responsive data tables.
- Touch-friendly controls.

Mobile:

- Compact navigation.
- Responsive dashboards.
- Operational forms.
- Limited administrative workflows where appropriate.

8.3 UX Standards

- Consistent navigation.
- Clear visual hierarchy.
- Search and filtering.
- Pagination.
- Form validation.
- Confirmation before sensitive actions.
- Loading and empty states.
- Error messages with corrective guidance.
- Accessible color contrast.
- Responsive layouts.

---

9. BUSINESS WORKFLOWS

9.1 Sales Workflow

Cashier Login
→ Open Register
→ Verify Eligibility
→ Select Products
→ Validate Price and Stock
→ Checkout
→ Process Payment
→ Confirm Payment
→ Commit Sale
→ Append Stock Movement
→ Generate Receipt
→ Update Reporting

Sale completion must be atomic from the application's perspective.

Payment provider integration must use idempotency and reconciliation to prevent duplicate charges or duplicate sale recording.

9.2 Cash Closing Workflow

Cashier submits closing count
→ System calculates expected cash
→ System calculates variance
→ Supervisor reviews
→ Finance verifies according to policy
→ Session closes
→ Reconciliation record is retained.

9.3 Stock Adjustment Workflow

Count stock
→ Compare with system
→ Record discrepancy
→ Investigate
→ Submit adjustment request
→ Approval
→ Append stock movement
→ Update stock balance
→ Close investigation.

9.4 Purchase Workflow

Purchase Requisition
→ Approval
→ Purchase Order
→ Supplier Confirmation
→ Goods Receiving
→ Quantity and Quality Verification
→ Invoice Matching
→ Stock Posting
→ Accounts Payable.

9.5 Audit Workflow

Audit Planning
→ Audit Assignment
→ Evidence Collection
→ Examination
→ Findings
→ Management Response
→ Corrective Action
→ Verification
→ Audit Closure.

---

10. API SPECIFICATION

Base path: /api/v1

Core endpoints:

Authentication:

- POST /auth/login
- POST /auth/logout
- GET /auth/me

Users:

- GET /users
- POST /users
- GET /users/:id
- PATCH /users/:id

Branches:

- GET /branches
- POST /branches
- PATCH /branches/:id

Products:

- GET /products
- POST /products
- PATCH /products/:id

Inventory:

- GET /inventory/balances
- GET /inventory/movements
- POST /inventory/adjustments

POS:

- POST /sales
- GET /sales
- GET /sales/:id
- POST /sales/:id/refunds
- POST /sales/:id/reversals

Warehouse:

- POST /stock-transfers
- POST /stock-transfers/:id/dispatch
- POST /stock-transfers/:id/receive

Finance:

- GET /finance/reports
- POST /finance/expenses
- GET /finance/reconciliation

HR:

- GET /employees
- POST /employees
- GET /attendance
- POST /attendance

Audit:

- GET /audit/logs
- POST /audit/findings
- POST /audit/corrective-actions

Approvals:

- GET /approvals
- POST /approvals
- POST /approvals/:id/decisions

Reports:

- GET /reports/sales
- GET /reports/inventory
- GET /reports/branches

All mutation endpoints must validate identity, permission, organization scope, branch scope, business rules, and request payloads.

---

11. SECURITY ARCHITECTURE

Mandatory controls:

- HTTPS/TLS.
- Secure authentication.
- HttpOnly and Secure cookies.
- SameSite session policy.
- Password hashing with Argon2id.
- MFA for privileged accounts.
- Login rate limiting.
- Session revocation.
- RBAC.
- Branch-level authorization.
- CSRF protection where applicable.
- Input validation.
- SQL injection protection.
- XSS protection.
- Security headers.
- Secrets management.
- Encrypted backups.
- Audit trails.
- Vulnerability testing.

Sensitive operations must be recorded.

Audit logs must be protected against unauthorized modification and deletion. High-assurance deployments should replicate audit events to separately controlled storage.

Data Privacy

Personal employee information, customer information, and financial data must be processed under applicable privacy requirements, including Indonesia's Personal Data Protection Law (UU PDP).

Data access must follow purpose limitation and least privilege.

---

12. NON-FUNCTIONAL REQUIREMENTS

Initial engineering targets, subject to validation through load testing:

Performance:

- Standard API read response: p95 ≤ 500 ms under agreed load.
- Standard API write response: p95 ≤ 800 ms excluding external providers.
- Dashboard first useful render: ≤ 3 seconds under agreed network conditions.
- Search and filtering must support paginated queries.

Availability:

- Initial target: 99.5% monthly service availability.
- Production recovery objectives must be approved.
- Target RPO: 15 minutes.
- Target RTO: 4 hours.

Scalability:

- Configurable branch count.
- Configurable user count.
- Horizontal scaling for stateless application instances.
- Database connection pooling.
- Queue-based background processing.

Reliability:

- Transaction atomicity.
- Idempotent operations.
- Automated backups.
- Restore testing.
- Error monitoring.
- Health checks.

All targets must be verified in the actual deployment environment.

---

13. OFFLINE AND NETWORK STRATEGY

Initial architecture is cloud-based.

POS should support a controlled offline capability in a later implementation phase.

Offline requirements:

- Secure local application storage.
- Cached eligible product catalog.
- Device registration.
- Local transaction queue.
- Unique transaction identifiers.
- Idempotent synchronization.
- Conflict detection.
- Sync status monitoring.
- No silent overwriting of central records.

Important restrictions:

- Offline sales must follow explicitly approved business and legal policies.
- Inventory reservations and offline stock cannot be assumed globally accurate.
- Restricted transactions must not bypass mandatory verification.
- Payment status must never be falsely reported as confirmed.

Offline mode must undergo separate acceptance testing.

---

14. REPORTING AND KPI FRAMEWORK

Sales KPI

- Total revenue.
- Number of transactions.
- Average transaction value.
- Gross sales.
- Discounts.
- Refund ratio.

Inventory KPI

- Stock accuracy.
- Stock turnover.
- Inventory aging.
- Out-of-stock rate.
- Stock discrepancy value.
- Slow-moving inventory.

Finance KPI

- Gross profit.
- Net profit.
- Expense ratio.
- Cash variance.
- Settlement delay.
- Accounts payable aging.

HR KPI

- Attendance rate.
- Late attendance.
- Absence rate.
- Overtime.
- Employee turnover.
- Productivity metrics.

Audit KPI

- Number of findings.
- Critical findings.
- Corrective action completion.
- Overdue findings.
- Repeat findings.

Branch KPI

- Revenue.
- Profitability.
- Transaction count.
- Average transaction value.
- Stock accuracy.
- Operational compliance.

Every KPI must have a documented calculation formula, source tables, refresh interval, and accountable data owner.

---

15. DEVELOPMENT ROADMAP

Phase 0 — Project Foundation

- Requirements validation.
- System architecture.
- UX wireframes.
- Design system.
- Database modeling.
- Development standards.

Phase 1 — Core Platform

- Authentication.
- User management.
- Organization.
- Branch management.
- RBAC.
- Database migrations.

Phase 2 — Retail Core

- Product management.
- POS.
- Payment records.
- Receipts.
- Cash sessions.
- Transaction history.

Phase 3 — Inventory & SCT

- Stock ledger.
- Inventory balances.
- Cycle count.
- Discrepancy management.
- Stock adjustments.

Phase 4 — Warehouse & Procurement

- Suppliers.
- Purchase orders.
- Goods receiving.
- Transfers.
- Distribution.

Phase 5 — Finance

- Expenses.
- Cash reconciliation.
- Financial journals.
- Settlement reconciliation.
- Financial reports.

Phase 6 — HR & Audit

- Employees.
- Attendance.
- Shift scheduling.
- Audit management.
- Corrective actions.

Phase 7 — Executive & BI

- Executive dashboard.
- Consolidated reports.
- KPI.
- Branch comparison.
- Alerts.

Phase 8 — Enterprise Hardening

- Security testing.
- Load testing.
- Backup and recovery.
- Offline capability.
- Monitoring.
- Production deployment.

---

16. TESTING AND QUALITY ASSURANCE

Mandatory testing categories:

1. Unit testing.
2. Integration testing.
3. API testing.
4. Database integrity testing.
5. Authorization testing.
6. End-to-end testing.
7. POS transaction testing.
8. Inventory reconciliation testing.
9. Financial reconciliation testing.
10. Performance testing.
11. Security testing.
12. Backup restoration testing.
13. User acceptance testing.

Critical scenarios must include:

- Duplicate checkout request.
- Payment provider timeout.
- Payment confirmed but client disconnected.
- Concurrent sales of limited stock.
- Partial stock transfer.
- Partial goods receiving.
- Unauthorized refund.
- Unauthorized stock adjustment.
- Cash closing variance.
- Branch access violation.
- Database interruption during transaction.

---

17. ACCEPTANCE CRITERIA

A module cannot be declared complete solely because its interface exists.

Each module must satisfy:

- Functional requirements implemented.
- Business rules enforced in backend.
- Database constraints verified.
- Authorization tested.
- Audit trail implemented.
- Error handling implemented.
- Integration tested.
- Documentation completed.
- UAT approved.
- No unresolved critical defects.

Production release requires:

- Security sign-off.
- Data migration validation.
- Backup and recovery validation.
- Operational readiness.
- User training.
- Deployment approval.

---

18. PROJECT GOVERNANCE

The MPS is the authoritative baseline for project scope and system behavior.

Every feature must have:

- Requirement ID.
- Description.
- Business owner.
- Technical owner.
- Priority.
- Acceptance criteria.
- Test case.
- Implementation status.

Change management:

1. Submit change request.
2. Document business justification.
3. Evaluate technical impact.
4. Evaluate security and compliance impact.
5. Evaluate cost and schedule impact.
6. Approve or reject.
7. Update affected specifications.
8. Update version history.

No developer may silently change a critical business rule.

Document hierarchy

1. Master Project Specification (MPS).
2. System Architecture Document (SAD).
3. Software Requirements Specification (SRS).
4. Database Design Document (DDD).
5. API Specification.
6. UI/UX Design System.
7. Security Specification.
8. Test Plan.
9. Deployment and Operations Manual.

Lower-level documents must remain consistent with this MPS.

---

19. OUT OF SCOPE UNTIL SEPARATELY APPROVED

The following are not automatically included in the initial release:

- Customer mobile application.
- E-commerce marketplace.
- Loyalty and rewards program.
- AI forecasting.
- Advanced fraud detection.
- External accounting integrations.
- Advanced BI warehouse.
- Multi-country tax configuration.
- Dedicated mobile application.

These can be added through formal change requests.

---

20. FINAL PROJECT DIRECTIVE

VAPECORE POS must be developed as an integrated enterprise retail operating system with strict data integrity, transparent operations, accountable access control, and scalable cloud infrastructure.

The primary objective is to create a reliable system of record for company operations.

The system must ensure that:

- Every sale is traceable.
- Every stock movement is accountable.
- Every financial entry is reconcilable.
- Every approval is documented.
- Every user action is attributable.
- Every branch operates under consistent policies.
- Every management report can be traced to its underlying records.

FINAL BASELINE: MPS-VCP-001 / VERSION 1.0.0

This specification becomes the primary project reference. Any change to its approved scope, architecture, security principles, or critical business rules must follow formal change management.

END OF MASTER PROJECT SPECIFICATION
