# Shopping API

A robust backend platform managing the core e-commerce lifecycle, from product catalog and inventory management to cart state and order processing. This project was fully hand-built without vibe coding.

## 🏗 Architecture & Domain Boundaries

The system is built on **Clean/Onion Architecture**, enforcing strict isolation between enterprise logic, application orchestration, and infrastructure. State mutations and data retrieval are strictly separated using the **CQRS** pattern to prevent complex domain logic from bleeding into read paths.

### Bounded Contexts

*   **Identity & Access:** Manages user authentication, authorization, and tenant/role claims.
*   **Catalog:** Owns product definitions, categorization, pricing, and availability. Optimized for high-frequency reads.
*   **Cart & Checkout:** Manages temporary state for active shopping sessions. Highly volatile, prioritizing write throughput before safely transitioning to a durable order.
*   **Order & Fulfillment:** The authoritative ledger for completed transactions, payment states, and fulfillment tracking.

## ⚙️ Core Technologies

*   **Engine:** ASP.NET Core Web API (.NET 8+)
*   **Data & Orchestration:** Entity Framework Core (EF Core), MediatR
*   **Security:** ASP.NET Core Identity
*   *(Add target database provider, e.g., PostgreSQL, SQL Server)*

## 🚀 Getting Started

### Prerequisites

*   .NET 8.0 SDK (or current version)
*   *(Target Database Engine)*

### Local Setup

1. **Clone the repository:**
   ```bash
   git clone [https://github.com/Jafarli-Mahammad/Shopping.git](https://github.com/Jafarli-Mahammad/Shopping.git)
   cd Shopping
