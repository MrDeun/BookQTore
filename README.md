# BookQTore

A simple desktop library management application built with **Qt 5/6** and **SQLite** (in-memory).

## Features

- **Books** — Add, remove, and browse a catalog of books (title, author).
- **Persons** — Add, remove, and browse a directory of people (name, surname, phone, email).
- **Borrowing** — Borrow a book to a person (auto-sets due date to +1 month) and return it.
- **Dual-view UI** — Switch between Books and Persons views with context-sensitive buttons.
- **Detail pane** — See full info and current borrowing status for the selected item.

## Build

Requires **CMake ≥ 3.16** and Qt 5 or Qt 6 with `Widgets` and `Sql` modules.

```bash
mkdir build && cd build
cmake ..
cmake --build .
./bookqtore
```

## Architecture

- **C++17** with CMake build system
- Qt Designer `.ui` files compiled via `AUTOUIC` / `AUTOMOC`
- Repository pattern with static helper classes (`BookRepository`, `PersonRepository`, `BorrowingRepository`)
- SQLite in-memory database created on startup
- Domain model classes: `Book`, `Person`, `Borrowing`
- Modal dialogs for add/borrow/return operations
