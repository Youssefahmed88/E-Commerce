# E-Commerce

A Java OOP simulation of an online store covering inventory management, shopping cart, and checkout flow.

## Design Highlights

- **Shippable Interface:** Products implement `Shippable` to differentiate physical vs. digital items, keeping shipping fee logic decoupled.
- **Two-Pass Stock Validation:** Cart validates all item quantities before reducing stock — prevents partial deductions on failure.
- **Separation of Concerns:** `Cart`, `Inventory`, `Customer`, and `ShippingService` each own a single responsibility.

## Structure

```
src/
├── Product.java          # Product entity with Shippable interface
├── Cart.java             # Cart management + checkout logic
├── CartItem.java         # Item wrapper with quantity
├── Customer.java         # Buyer with balance and checkout
├── Inventory.java        # Stock management
├── Shippable.java        # Interface for shippable products
├── ShippingService.java  # Shipping fee calculation
└── Main.java             # Demo and test cases
```

## Run

```bash
javac src/*.java
java src.Main
```
