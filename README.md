# Product Vision

## Product Name

Inventory Management System

## Vision Statement

Provide a simple internal platform that helps small or mid-sized operations teams track products, monitor stock levels, manage supporting master data, and control sensitive changes through approval workflows and reporting.

## Problem Statement

Inventory operations often depend on manual spreadsheets or disconnected tools. That leads to:

- Poor visibility into current stock
- Delayed response to low-stock situations
- Weak control over who can change inventory data
- Limited reporting for stock, sales, and user activity
- Errors when categories, suppliers, and users are managed informally

## Target Users

### Admin

- Manages products, categories, suppliers, and users
- Reviews and approves operational requests
- Uses dashboards and exports to monitor the business
- Needs traceability through user audit and stock movement history

### Standard User

- Views inventory and low-stock data
- Requests stock changes and new categories
- Uses a limited dashboard and account controls
- Needs a fast workflow without direct access to admin-only operations

## Business Goals

- Centralize inventory records in one application
- Reduce stock-out risk through alerts and low-stock views
- Introduce controlled approval for sensitive updates
- Improve operational reporting and export capability
- Track user access for accountability

## Product Goals

- Make daily inventory status visible within one dashboard
- Ensure stock changes are captured consistently
- Support search, filtering, and quick navigation across records
- Provide role-based authorization with minimal complexity
- Keep the system deployable on a standard Spring Boot plus MySQL setup

## In-Scope Features

- Authentication with role-based access control
- Admin and user dashboards
- Product CRUD and image upload
- Inventory listing, search, and category filtering
- Low-stock detection and stock quantity updates
- Category CRUD
- Supplier CRUD
- User management and profile updates
- Change password flow
- Approval requests for stock updates and category creation
- Sales, stock movement, and user audit reporting
- Excel exports
- Email notification for low-stock products

## Out-of-Scope for Current Release

- Purchase order lifecycle
- Barcode scanning
- Multi-warehouse support
- API-first external integrations
- Mobile application
- Advanced analytics or forecasting
- Fine-grained workflow configuration

## Success Metrics

- Stock records can be created, updated, searched, and exported without manual DB edits
- Low-stock items are visible and trigger notification logic
- Admin-only functions remain inaccessible to standard users
- Approval requests can be created and resolved end to end
- Reports are downloadable in spreadsheet form

## Constraints and Assumptions

- Requires a MySQL database named `inventory_db`
- Runs on port `9090` by default
- Uses local filesystem image storage at `C:/inventory-images/`
- Current mail delivery depends on configured SMTP credentials
- Current seeded users create one admin and one standard user on startup

## Risks

- Secrets are stored in `application.properties`, which is not production-safe
- Image storage path is hardcoded and Windows-specific
- There is limited visible automated test coverage
- Report and dashboard quality depend on underlying sales and movement data integrity
