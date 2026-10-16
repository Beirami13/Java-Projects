# Shop

A small Java project that models shop products and uses the Streams API to build reports over a list of products.

## What it contains

| File | Purpose |
|------|---------|
| `Product.java` | Base class with `name` and `price`; overrides `equals`, `hashCode` and `toString` |
| `Book.java` | Extends `Product`; adds `title` and `author` |
| `Pen.java` | Extends `Product`; adds a `Color` enum (`Red`, `Blue`, `Black`, `Green`) |
| `Pair.java` | A generic `Pair<T, U>` holding a key and a value |
| `ProductTools.java` | Stream-based helper methods |
| `Main.java` | Demo that creates sample products and runs the tools |

## Tools in `ProductTools`

- `printSorted(products)` removes duplicates (using `equals`/`hashCode`) and prints the products sorted by name, then by price.
- `printExpensive(products)` returns a `Pair` with the most expensive book and the most expensive pen.
- `ShoeColor(products)` counts the pens of each color and prints the result.

## Requirements

- JDK 8 or newer

## How to run

From the `untitled/src` folder:

```bash
javac Shop/*.java
java Shop.Main
```

`Main` currently runs `ShoeColor`. To try the other tools, uncomment the `printSorted` or `printExpensive` lines in `Main.java`.

## Concepts practiced

- Inheritance and `super` constructors
- Enums
- Generics (`Pair<T, U>`)
- Overriding `equals` and `hashCode` so `distinct()` works
- Streams: `filter`, `map`, `max`, `sorted`, `distinct`, `count`
- `Comparator.comparing(...).thenComparingInt(...)`

## Known limitations

- `Main` uses hard-coded sample data; there is no user input.
- `ShoeColor` repeats the same stream four times; it could be simplified with `Collectors.groupingBy`.