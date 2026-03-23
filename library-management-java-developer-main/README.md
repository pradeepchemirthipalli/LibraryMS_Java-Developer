# 📚 LibraryMS — Library Management System

> A fully functional, standalone HTML-based Library Management System built as a Java Developer Intern project. Demonstrates core Java OOP principles, design patterns, and clean architecture — all in a single browser-ready file.

---

## 🚀 Getting Started

No installation, server, or build tools required.

1. Download `library-management-system.html`
2. Open it in any modern browser (Chrome, Firefox, Edge, Safari)
3. The system loads with pre-populated sample data ready to explore

---

## ✨ Features

### 📚 Book Management
- Add, edit, and delete book records
- Track total copies vs available copies in real time
- Search books by title, author, or ISBN
- Filter by genre (Programming, Algorithms, Design Patterns, etc.)
- Visual availability badges: Available / Partial / Fully Borrowed

### 👤 Member Management
- Register new members with name, email, and phone
- View borrowing history per member
- Remove members (blocked if they have unreturned books)
- Search members by name, ID, or email

### 🔄 Transaction Management
- Issue books to members with automatic date tracking (14-day default loan)
- Enforce a 3-book borrow limit per member
- Return books with one click — updates availability instantly
- Filter transactions by status: Issued / Overdue / Returned
- Red overdue banner with details of all late returns

### 📊 Dashboard Stats
- Live counters for: Total Book Titles, Members, Books Issued, Overdue Returns
- Colour-coded stat cards that update after every action

### 🔔 Toast Notifications
- Non-intrusive success/error/info toasts for every user action

---

## ☕ Java Design Patterns Tab

The **Java Design** tab contains six annotated, interview-ready code snippets covering:

| Pattern | Key Concepts |
|---|---|
| **Book Entity** | Encapsulation, private fields, method contracts, `toString()` |
| **Member (Inheritance)** | Abstract class, `@Override`, Polymorphism, `extends` |
| **Repository Pattern** | Interface-based design, Java 8 Streams, method references, `Optional` |
| **Service Layer** | Dependency Injection (constructor injection), SOLID principles, `orElseThrow` |
| **Singleton Pattern** | `volatile`, `synchronized`, double-checked locking, thread safety |
| **Custom Exceptions** | Checked vs unchecked exceptions, exception hierarchy, `RuntimeException` |

These snippets are directly relevant to Java internship interviews and reflect real-world enterprise architecture.

---

## 🗂️ Project Structure

```
library-management-system.html
│
├── HTML Structure
│   ├── Header (branding + badge pills)
│   ├── Stats Dashboard (4 live metric cards)
│   ├── Overdue Alert Banner
│   ├── Tab Navigation (Books / Members / Transactions / Java Design)
│   └── Modal (Add / Edit / Issue forms)
│
├── CSS (embedded)
│   ├── Dark theme with CSS variables
│   ├── JetBrains Mono + Syne fonts
│   ├── Responsive grid layout
│   └── Animations (fade, slide, toast)
│
└── JavaScript (embedded)
    ├── In-memory data store (books, members, transactions arrays)
    ├── CRUD operations for all entities
    ├── Real-time search and filter logic
    ├── Borrow / return workflow with validation
    ├── Overdue detection engine
    └── Java code snippet renderer
```

---

## 🏗️ Architecture Overview (Java Equivalent)

The frontend logic mirrors a standard Java layered architecture:

```
┌─────────────────────────────────────┐
│            UI Layer (HTML/CSS)       │  ← View / Controller
├─────────────────────────────────────┤
│         Service Layer (JS)           │  ← LibraryService.java
│  issueBook() / returnBook() / CRUD   │
├─────────────────────────────────────┤
│       Repository Layer (JS)          │  ← BookRepository.java
│    In-memory Map / Array Store       │
├─────────────────────────────────────┤
│          Entity Layer (JS)           │  ← Book.java / Member.java
│    books[] / members[] / txns[]      │
└─────────────────────────────────────┘
```

---

## 📋 Data Model

### Book
| Field | Type | Description |
|---|---|---|
| `id` | String | Auto-generated (B001, B002…) |
| `isbn` | String | ISBN-13 identifier |
| `title` | String | Book title |
| `author` | String | Author name |
| `genre` | String | Genre category |
| `copies` | Number | Total copies owned |
| `available` | Number | Copies currently available |

### Member
| Field | Type | Description |
|---|---|---|
| `id` | String | Auto-generated (M001, M002…) |
| `name` | String | Full name |
| `email` | String | Email address |
| `phone` | String | Phone number |
| `borrowed` | Number | Active borrow count |
| `joined` | String | Registration date (YYYY-MM-DD) |

### Transaction
| Field | Type | Description |
|---|---|---|
| `id` | String | Auto-generated (T001, T002…) |
| `memberId` | String | Reference to member |
| `bookId` | String | Reference to book |
| `issue` | String | Issue date (YYYY-MM-DD) |
| `due` | String | Due date (14 days after issue) |
| `returned` | Boolean | Return status |

---

## 🔒 Business Rules

- A member may borrow a maximum of **3 books** at a time
- A book can only be issued if `available > 0`
- A member cannot be deleted while they have unreturned books
- A transaction is marked **overdue** if `due date < today` and `returned = false`
- Returning a book increments `available` and decrements the member's `borrowed` count

---

## 🛠️ Technologies Used

| Technology | Purpose |
|---|---|
| HTML5 | Structure and semantic markup |
| CSS3 | Dark theme, animations, responsive layout |
| Vanilla JavaScript (ES6+) | All logic, state management, DOM rendering |
| JetBrains Mono | Monospace font for code aesthetic |
| Syne | Display font for headings |
| Google Fonts CDN | Font delivery |

> No frameworks, no dependencies, no build step — just open and run.

---

## 🎯 Skills Demonstrated (Intern Interview Relevance)

- **Object-Oriented Programming** — encapsulation, inheritance, polymorphism, abstraction
- **Design Patterns** — Singleton, Repository, Service Layer (layered architecture)
- **SOLID Principles** — especially Single Responsibility and Dependency Inversion
- **Java 8+ Features** — Streams API, `Optional`, method references, lambda expressions
- **Exception Handling** — custom checked/unchecked exception hierarchy
- **Data Structures** — in-memory HashMap-style store, array filtering and searching
- **Clean Code** — separation of concerns, meaningful naming, modular functions

---

## 📸 Screenshots

| Books Panel | Transactions Panel | Java Design Panel |
|---|---|---|
| Search, filter, CRUD | Issue & return workflow | Annotated code snippets |

---

## 🔮 Potential Enhancements

- Persistent storage using `localStorage` or IndexedDB
- Export data to CSV / PDF
- Fine calculation for overdue books
- Role-based access (Admin vs Librarian)
- REST API backend integration (Spring Boot)
- Unit tests with JUnit 5 / Mockito
- Barcode / ISBN scanner integration

---

## 👨‍💻 Author

Built as a **Java Developer Intern** portfolio project showcasing full-stack thinking, OOP design, and clean UI development.

---

## 📄 License

This project is open for educational and portfolio use.
