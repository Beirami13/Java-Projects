# University Library Management System

A menu-driven console application that manages a university library. It supports four types of users (guest, student, staff and manager) and stores its data in plain text files.

## Features

### Guest
- Search a book by title
- View the number of registered students
- View simple library statistics (students, books, borrow requests, currently borrowed books)

### Student
- Register and log in
- View and edit personal information (name and password)
- Search books
- Request to borrow a book and return a borrowed book
- View the list of available books

### Staff
- Log in and change password
- Register new books and edit existing ones
- Approve borrow requests
- Receive returned books
- View a student's borrow history and library statistics
- Activate or deactivate a student account

### Manager
- Register new staff members
- View borrow statistics and student statistics
- View the borrow history of an individual student
- View the students with the most delayed returns

## How a borrow works

1. A student sends a borrow request for an available book.
2. The request is saved with the status `PENDING`.
3. A staff member approves it (`APPROVED` / `BORROWED`) or rejects it (`REJECTED`).
4. When the book comes back, a staff member receives it and the request becomes `RETURNED`. Late days are calculated from the end date.

## Requirements

- JDK 8 or newer

## How to run

From the `untitled/src` folder:

```bash
javac LibraryUniversity/*.java
java LibraryUniversity.LibrarySystem
```

Data files are created in the folder you run the command from, so always run it from the same place.

### Default manager account

On the first run the system creates a manager account:

| Username | Password |
|----------|----------|
| `manager` | `admin123` |

This is only for local testing.

## Project structure

```text
LibraryUniversity/
├── LibrarySystem.java   # entry point and main facade for the whole system
├── MenuHandler.java     # all console menus
├── Library.java         # shared interface
├── Person.java          # abstract base class for users
├── Student.java         # extends Person
├── Staff.java           # extends Person
├── Manager.java         # extends Person
├── Book.java            # book model
├── BorrowRequest.java   # borrow request model with a status
├── BookManager.java     # books, borrowing, returning, statistics
├── StudentManager.java  # student registration, login, updates
└── StaffManager.java    # staff registration and login
```

## Data files

The app reads and writes these plain text files in the working directory:

- `books.txt`
- `students.txt`
- `staff.txt`
- `borrows.txt`
- `borrow_requests.txt`

## OOP concepts used

- Abstract class (`Person`) with three subclasses
- Interface (`Library`) implemented by several classes
- Separate manager classes for each responsibility
- Encapsulation and input validation
- `java.time.LocalDate` for borrow dates and delay calculation

## Known limitations

- Passwords are stored as plain text and the default manager password is hard-coded.
- Data is stored in text files, not a database.
- The "View Staff Performance" report is not implemented yet.
- There is no automated test suite.

## Possible improvements

- Hash passwords
- Move storage to a database such as SQLite
- Add unit tests