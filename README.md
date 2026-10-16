<div align="center">

# ⚙️ In-Memory Subsystem (C++)

### Fixed-Capacity Library Inventory Management

**An educational C++ console application demonstrating array-based record management, CRUD operations, linear search, and structured procedural programming.**

![Language](https://img.shields.io/badge/Language-C%2B%2B-blue)
![Standard](https://img.shields.io/badge/Standard-C%2B%2B11-informational)
![Storage](https://img.shields.io/badge/Storage-In--Memory-success)
![Capacity](https://img.shields.io/badge/Capacity-50_Records-orange)
![License](https://img.shields.io/badge/License-MIT-green)

</div>

---

## 📌 Project Overview

The **In-Memory Subsystem** is a C++ command-line library inventory management application developed to explore fundamental concepts in data structures, record management, and procedural programming.

The system stores book records in a fixed-capacity array, supporting operations such as adding, searching, updating, deleting, displaying, and counting records.

Rather than relying on an external database, the application manages its records directly in memory during execution.

### Project Objectives

- Understand fixed-capacity array-based storage.
- Implement Create, Read, Update, and Delete (CRUD) operations.
- Apply linear search to locate records.
- Maintain record uniqueness through Book ID checks.
- Practice structured functions and menu-driven control flow.
- Explore the limitations of temporary in-memory storage.

This repository is intended as a learning and portfolio project, not a production-ready database or embedded storage engine.

---

## 🏗️ System Architecture

The application follows a single-process, menu-driven architecture.

User commands are processed through a continuous `while` loop and a `switch` statement.

Each supported operation is implemented in a separate function.

### Core Data Structure

```cpp
const int MAX = 50;

struct Book {
    int id;
    string title;
    string publishyear;
    string author;
    float price;
    int quantity;
};

Book books[MAX];
int countBooks = 0;
```

The system uses a global array with capacity for 50 book records.

The `countBooks` variable tracks the number of active records.

**Memory considerations:**

- The number of book records is limited to 50.
- Book records are stored in an array.
- Text fields use `std::string`, which may allocate memory dynamically.
- Records remain available only while the program is running.
- No database or file-based persistence is implemented.

---

## 🚀 Features

| Feature | Description |
|---|---|
| Add Book | Insert a book with its ID, title, publication year, author, price, and quantity |
| Display Books | Display stored book records |
| Search by ID | Locate a record using its Book ID |
| Update Book | Modify an existing book's price and quantity |
| Delete Book | Remove a record and shift subsequent records |
| Count Books | Display the number of active records |
| Search by Name | Search for a book using an exact title match |
| Exit | Terminate the application |

### Record Uniqueness

Before adding a new book, the application scans existing records to check whether the requested Book ID is already present.

If a matching ID exists, the insertion is rejected.

The application also checks whether the maximum record capacity has been reached.

---

## 📊 Algorithmic Complexity

Let `N` represent the number of active records.

| Operation | Time Complexity | Explanation |
|---|---|---|
| Add Book | O(N) | Checks existing IDs before insertion |
| Display Books | O(N) | Iterates through stored records |
| Search by ID | O(N) | Uses linear search |
| Search by Name | O(N) | Uses linear search with exact title matching |
| Update Book | O(N) | Searches for the ID before modifying fields |
| Delete Book | O(N) | Searches and shifts subsequent records |
| Count Books | O(1) | Reads the active record counter |

These complexities describe the record-level operations. String comparisons and copying can add costs depending on text length.

---

## 🛠️ Technical Specifications

| Component | Implementation |
|---|---|
| Programming Language | C++ |
| Language Standard | C++11 or later |
| Application Type | Console / CLI |
| Storage | Fixed-capacity array |
| Maximum Records | 50 |
| Record Model | C++ `struct` |
| Search Method | Linear search |
| Control Flow | `while` loop and `switch` statement |
| Persistence | None |
| External Libraries | None required |
| Database | Not required |

The project uses standard C++ facilities and does not require third-party packages.

---

## 💻 Installation and Execution

### Prerequisites

Install a C++ compiler supporting C++11 or later, such as GCC or Clang.

Git is required if you intend to clone the repository.

### 1. Clone the Repository

```bash
git clone https://github.com/abdullah-dev-stack/IN-MEMORY-SUBSYSTEM-CPP.git
```

### 2. Open the Project Directory

```bash
cd IN-MEMORY-SUBSYSTEM-CPP
```

### 3. Compile the Application

For Linux or macOS using GCC:

```bash
g++ -std=c++11 in_memory_subsystem.cpp -o bookstore
```

### 4. Run the Application

```bash
./bookstore
```

### Windows

Using MinGW-w64 GCC:

```bash
g++ -std=c++11 in_memory_subsystem.cpp -o bookstore.exe
```

Run the executable:

```powershell
.\bookstore.exe
```

---

## 🖥️ Console Interface

The application presents the following menu:

```text
===== Library Management System =====
1. Add Book
2. Display All Books
3. Search Book
4. Update Book
5. Delete Book
6. Count Books
7. Search by book name
8. Exit
Enter your choice:
```

### Example Workflow

1. Start the application.
2. Select `1` to add a book.
3. Enter the Book ID, title, publication year, author, price, and quantity.
4. Select `2` to display the stored records.
5. Select `3` to search by Book ID.
6. Select `4` to update price or quantity.
7. Select `5` to delete a record.
8. Select `6` to count active records.
9. Select `7` to search by exact book title.
10. Select `8` to exit.

All records are temporary and are lost when the program terminates.

---

## ⚠️ Current Limitations

This project is designed for educational use and has several known limitations:

- The application supports a maximum of 50 records.
- Data is not saved between program executions.
- Invalid numeric input is not comprehensively handled.
- Text searches require exact title matches.
- The program uses global variables for record storage.
- No automated test suite or CI pipeline is currently included.
- Monetary values use `float`, which is not ideal for production financial calculations.
- The application is not designed for concurrent access or production workloads.

These limitations provide opportunities for further learning and improvement.

---

## 🗺️ Future Development

Potential improvements include:

- [ ] Strengthen numeric input validation.
- [ ] Add automated tests for CRUD operations.
- [ ] Introduce file-based persistence.
- [ ] Improve record searching and filtering.
- [ ] Add GitHub Actions for automated builds.
- [ ] Refactor global state into a dedicated C++ class.
- [ ] Improve error handling and user feedback.
- [ ] Expand developer and contributor documentation.

These items are planned possibilities and are not part of the current implementation.

---

## 🎓 Learning Outcomes

Developing this project provides practical experience with:

- C++ structures and arrays.
- Function-based program organization.
- CRUD operation implementation.
- Linear search algorithms.
- Fixed-capacity data management.
- Console input and output.
- Record deletion through element shifting.
- Basic time-complexity analysis.
- Understanding the difference between temporary memory storage and persistent databases.

These fundamentals are relevant to further study in systems programming, embedded software, and application development.

---

## 📄 License

This project is distributed under the MIT License.

See the [LICENSE](LICENSE) file for details.

---

## 👨‍💻 Author

**Abdullah Khan**

Computer Science Undergraduate  
Interested in C++, Systems Programming, Software Engineering, and Practical Software Development.

[GitHub Profile](https://github.com/abdullah-dev-stack)

---

<div align="center">

**Built to strengthen fundamental programming and data-structure skills through practical C++ development.**

</div>
