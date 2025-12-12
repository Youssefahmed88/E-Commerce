# Java Project Showcase

A collection of Java projects demonstrating advanced OOP principles, design patterns, and clean software architecture.

## Repository Structure

| Project | Description | Key Technical Signal |
| :--- | :--- | :--- |
| [**Bookstore**](./Bookstore) | Advanced inventory management system. | Registry Pattern, OCP, Hybrid Storage |
| [**E-Commerce**](./E-Commerce) | High-fidelity store storefront simulation. | Interface Abstraction, Atomic Validation |

---

## Projects Overview

### 1. Bookstore (Advanced Architecture)
An extensible system designed for scalability, allowing the integration of diverse book types and purchase behaviors without disrupting core logic.

#### **Design Highlights**
- **Registry Pattern (OCP):** New book types (PDF, Paper, Audiobook, Comic) are registered via `BookTypeRegistry` using Functional Interfaces and Lambdas — ensuring zero core logic modifications for feature extensions.
- **Dual-Index Inventory:** Implemented a hybrid index system using ISBN (`HashMap` for $O(1)$ lookup) and Title-based search to optimize retrieval performance.
- **Two-Pass Safe Removal:** Managed outdated inventory using a two-pass collection-and-purge strategy to prevent `ConcurrentModificationException` during state transitions.
- **Validation:** Integrated comprehensive input sanitization for quantities, emails, and address formats with proper exception handling.

### 2. Simple E-Commerce (SOLID Principles)
A clean implementation of a retail simulation focusing on separation of concerns and data integrity.

#### **Design Highlights**
- **Shippable Interface:** Utilized interface-based abstraction to decouple physical shipping logic from digital asset delivery, ensuring a clean inheritance hierarchy.
- **Two-Pass Stock Validation:** Implemented an "All-or-Nothing" validation pass. The system verifies all cart item quantities before any inventory reduction, maintaining data consistency.
- **Separation of Concerns:** Rigidly decoupled responsibilities across `Cart`, `Inventory`, `Customer`, and `ShippingService` to ensure high maintainability and testability.
