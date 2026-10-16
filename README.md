# Java Projects

Object-oriented Java projects I built while learning core Java and OOP at university. Each project is a small console application with its own README.

## Projects

| Project | What it is | Main concepts |
|---------|------------|---------------|
| [LibraryUniversity](untitled/src/LibraryUniversity/README.md) | A university library management system with guest, student, staff and manager roles | Inheritance, abstract classes, interfaces, collections, file persistence, `java.time` |
| [Shop](untitled/src/Shop/README.md) | A small product model (books and pens) with stream-based reporting tools | Inheritance, enums, generics, `equals`/`hashCode`, Streams API |

## Requirements

- JDK 8 or newer (the code uses streams and `java.time`)
- No external libraries

## Repository structure

```text
Java-Projects/
├── README.md
└── untitled/
    └── src/
        ├── LibraryUniversity/   # library management system
        └── Shop/                # product model and stream tools
```

## How to run

Run all commands from the `untitled/src` folder.

```bash
cd untitled/src

# Library management system
javac LibraryUniversity/*.java
java LibraryUniversity.LibrarySystem

# Shop
javac Shop/*.java
java Shop.Main
```

You can also open the `untitled` folder in IntelliJ IDEA and run the `main` method of `LibrarySystem` or `Main`.

## What I practiced

- Designing class hierarchies and choosing between inheritance and interfaces
- Encapsulation with private fields, getters and setters, and input validation
- Storing data in plain text files and loading it back on startup
- Writing a menu-driven console interface
- Using the Streams API for filtering, sorting and grouping

## Known limitations

These are learning projects, not production software. The main limitations are listed in each project's README (for example, the library system stores passwords as plain text).