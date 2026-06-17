# Business Management Application

A console-based Java simulation of a food production company's supply chain. The application models the full flow from purchasing raw ingredients to producing and selling finished goods, with a shared company account tracking all financial transactions.

---

## Features

- **Buy ingredients** — Purchase Milk, Cacao, Cream, or Yeast from the market (deducted from company balance)
- **Ship to Factory** — Transfer raw materials from the Warehouse to the Factory
- **Produce products** — Factory consumes ingredients to manufacture Boxed Milk, Chocolate, or Yogurt
- **Ship to Distribution Center** — Move finished goods to the distribution hub
- **Sell products** — Distribution Center sells products and adds revenue to the company account
- **Financial tracking** — `AccountOfCompany` tracks money spent and earned across all operations

---

## Tech Stack

| | |
|---|---|
| Language | **Java 12** (JavaSE-12) |
| Interface | Console (Scanner) |
| IDE | Eclipse |

---

## Project Structure

```
src/
├── BusinessApplicationApp.java   # main() — entry point and menu loop
├── BusinessApplication.java      # Application bootstrap class
│
├── Facilities/
│   ├── AccountOfCompany.java     # Tracks company balance
│   ├── Warehouse.java            # Stores raw ingredients, handles purchasing
│   ├── Factory.java              # Consumes ingredients to produce products
│   ├── DistributionCenter.java   # Sells finished products
│   ├── Storage.java              # Base storage abstraction
│   ├── StorageArea.java          # Stores solid / packaged products
│   ├── StorageTank.java          # Stores liquid / bulk ingredients
│   ├── IngredientsBuyer.java     # Handles purchase logic and cost calculation
│   └── ProduceProduct.java       # Production recipes for each product type
│
├── Ingredients/
│   ├── RawMaterial.java          # Abstract base class
│   ├── Milk.java
│   ├── Cacao.java
│   ├── Cream.java
│   └── Yeast.java
│
└── Products/
    ├── Product.java              # Abstract base class (volume-based)
    ├── BoxedMilk.java            # Requires: Milk
    ├── Chocolate.java            # Requires: Milk + Cacao + Cream
    └── Yogurt.java               # Requires: Milk + Yeast
```

---

## Production Recipes

| Product | Ingredients Required |
|---|---|
| Boxed Milk | Milk |
| Chocolate | Milk + Cacao + Cream |
| Yogurt | Milk + Yeast |

---

## Ingredient Prices

| Ingredient | Price per unit |
|---|---|
| Milk | $0.25 |
| Cream | $0.30 |
| Cacao | $1.00 |
| Yeast | $5.00 |

---

## Menu

```
1) To buy ingredients
2) To ship ingredients to Factory
3) To produce product with ingredients
4) To ship products to Distribution Center
5) To sell products
0) To exit
```

---

## Getting Started

### Prerequisites

- **Java 12** (JavaSE-12)
- Eclipse IDE (`.classpath` and `.project` included) or any Java IDE

### Run with Eclipse

1. `File → Import → Existing Projects into Workspace`
2. Select the cloned folder
3. Run `BusinessApplicationApp.java` as a Java Application

### Run from the command line

```bash
javac -d bin src/**/*.java src/*.java
java -cp bin BusinessApplicationApp
```
