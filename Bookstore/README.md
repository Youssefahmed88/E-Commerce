# Bookstore

A type-extensible inventory and purchase management system built around SOLID design principles.

## Design Highlights

- **Registry Pattern (OCP):** New book types (PDF, Paper, Audiobook, Comic) are registered via `BookTypeRegistry` using Functional Interfaces and Lambdas — no core logic changes required.
- **Dual-Index Inventory:** Books are indexed by both ISBN (`O(1)` lookup) and Title for fast retrieval.
- **Two-Pass Removal:** Outdated books are collected then removed in a separate pass to avoid `ConcurrentModificationException`.
- **Validation:** Input checks on quantity, email, address, and stock availability with proper exception handling.

## Structure

```
src/
├── Book.java               # Book entity + delivery delegation
├── BookTypeHandler.java     # Functional interface for purchase behavior
├── BookTypeRegistry.java    # Registry for pluggable delivery handlers
├── Customer.java            # Buyer logic and checkout flow
├── Inventory.java           # Stock management with dual-index
├── StockItem.java           # Wrapper for book + quantity
└── Main.java                # Test cases
```

## Run

```bash
javac src/*.java
java -cp src Main
```