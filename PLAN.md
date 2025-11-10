# Build Plan — JBudget (November 2025 → May 2026)

This plan turns learning milestones into weekly deliverables. Each week introduces core Java topics and implements a concrete piece of the budgeting app. Packages under `com.aspauldingcode.weekXX_*` hold the code for the week. You can keep earlier code and refactor progressively.

Below, each week lists the concrete classes/records, GUI elements (when applicable), and data structures to create so you have a hands-on blueprint.

## Milestones by Week

### Week 01 — Setup
  - Package: `week01_setup`
  - Classes: `EnvironmentCheck` (prints JDK, Maven info)
  - Data: none
  - GUI: none
  - Deliverable: JDK 25 recognized, `Main` runs; IDE/Maven aligned.

### Week 02 — Basics (types, variables, I/O)
  - Package: `week02_basics`
  - Classes: `InputDemo`, `MathDemo`, `StringDemo`
  - Data: primitives, `String`
  - GUI: none
  - Deliverable: Console demos for basic types and I/O.

### Week 03 — Control Flow
  - Package: `week03_control_flow`
  - Classes: `ConsoleMenu`, `ValidationUtils`
  - Data: menu states (enums)
  - GUI: none
  - Deliverable: Prototype console menu to add/view dummy transactions.

### Week 04 — Methods & Recursion
  - Package: `week04_methods_recursion`
  - Classes: `DateUtils`, `AmountUtils`, `RecursionExamples`
  - Data: `LocalDate`
  - GUI: none
  - Deliverable: Utility methods used by later modules.

### Week 05 — OOP Basics
  - Package: `week05_oop_basics`
  - Classes: `User`, `Account`
  - Data: `List<Account>` in `User`
  - GUI: none
  - Deliverable: Users can hold multiple accounts (no transactions yet).

### Week 06 — Encapsulation
  - Package: `week06_encapsulation`
  - Classes: `Money` (value object), `Category` (enum), `Budget`
  - Data: `Map<Category, Budget>`
  - GUI: none
  - Deliverable: Safe setters/getters; validated budget amounts.

### Week 07 — Inheritance & Polymorphism
  - Package: `week07_inheritance_polymorphism`
  - Classes: `Transaction` (abstract/base), `Income`, `Expense`, `Transfer`
  - Data: `List<Transaction>` per `Account`
  - GUI: none
  - Deliverable: Polymorphic transaction hierarchy (classic OOP).

### Week 08 — Collections
  - Package: `week08_collections`
  - Classes: `TransactionRepository`, `InMemoryDatabase`
  - Data: `Map<String, Account>`, `List<Transaction>`
  - GUI: none
  - Deliverable: Efficient storage/retrieval patterns with collections.

### Week 09 — Generics
  - Package: `week09_generics`
  - Classes: `Result<T>`, `Repository<TId, TEntity>` (interfaces)
  - Data: typed repositories
  - GUI: none
  - Deliverable: Reusable generic abstractions.

### Week 10 — Lambdas
  - Package: `week10_lambdas`
  - Classes: `TransactionFilter` (functional interface), `Callbacks`
  - Data: predicates and comparators
  - GUI: none
  - Deliverable: Lambda-powered filtering and sorting.

### Week 11 — Streams & Optional
  - Package: `week11_streams_optional`
  - Classes: `ReportService`, `Summary`
  - Data: stream pipelines, `Optional<Budget>`
  - GUI: none
  - Deliverable: Monthly/category summaries and aggregations.

### Week 12 — Records & Sealed Types
  - Package: `week12_records_sealed`
  - Records: `IncomeRecord`, `ExpenseRecord`, `TransferRecord`
  - Sealed: `sealed interface TxRecord permits IncomeRecord, ExpenseRecord, TransferRecord`
  - Data: immutable transaction snapshots
  - GUI: none
  - Deliverable: Modern immutable models alongside classic OOP types.

### Week 13 — Pattern Matching, Switch Expressions, Text Blocks
  - Package: `week13_pattern_matching_textblocks`
  - Classes: `Formatter`, `PatternMatchingExamples`
  - Data: text block templates
  - GUI: none
  - Deliverable: Pretty-printed reports using modern control flow.

### Week 14 — File I/O
  - Package: `week14_file_io`
  - Classes: `CsvExporter`, `CsvImporter`
  - Data: CSV rows for accounts/transactions
  - GUI: none
  - Deliverable: Export/import basic data.

### Week 15 — Serialization & JSON (Jackson)
  - Package: `week15_serialization_json`
  - Classes: `JsonStore`, `JsonMapper`
  - Data: JSON files; DTO records
  - GUI: none
  - Deliverable: Persist and restore app state.

### Week 16 — Threads & Executors
  - Package: `week16_threads_executors`
  - Classes: `TransactionSimulator`, `BackgroundTasks`
  - Data: thread-safe collections
  - GUI: none
  - Deliverable: Concurrent transaction simulation.

### Week 17 — Structured Concurrency
  - Package: `week17_structured_concurrency`
  - Classes: `TasksOrchestrator`
  - Data: scoped tasks
  - GUI: none
  - Deliverable: Clean orchestration of background jobs.

### Week 18 — JavaFX Basics
  - Package: `week18_javafx_basics`
  - GUI: `MainWindow`, layout panes, basic controls
  - Classes: `AppLauncher` (JavaFX), `ViewModel` stubs
  - Data: observable lists
  - Deliverable: GUI skeleton launches.

### Week 19 — JavaFX Events
  - Package: `week19_javafx_events`
  - GUI: forms to add transactions/accounts
  - Classes: `EventHandlers`, `FormValidators`
  - Data: bound properties
  - Deliverable: Interactive forms wired to view models.

### Week 20 — JavaFX Tables & Charts
  - Package: `week20_javafx_tables_charts`
  - GUI: `TransactionsTable`, `CategoryChart`
  - Classes: `TableAdapters`, `ChartSeriesBuilder`
  - Data: observable table models
  - Deliverable: Visual summaries and lists.

### Week 21 — GUI Integration
  - Package: `week21_gui_integration`
  - GUI: connect views to services (`ReportService`, `JsonStore`)
  - Classes: `Controllers`, `Bindings`
  - Data: application state model
  - Deliverable: Functional end-to-end UI.

### Week 22 — HttpClient
  - Package: `week22_httpclient`
  - Classes: `ExchangeRateClient`
  - Data: remote JSON parsing
  - GUI: optional rates widget
  - Deliverable: External data fetch.

### Week 23 — Networking Integration
  - Package: `week23_network_integration`
  - Classes: `SyncService`, `RateApplier`
  - Data: merged state
  - GUI: refresh controls
  - Deliverable: Remote data affects budgets and reports.

### Week 24 — Testing (JUnit)
  - Package: `week24_testing_junit`
  - Classes: `BudgetTests`, `TransactionTests`, `ReportTests`
  - Data: test fixtures
  - GUI: none
  - Deliverable: Reliable core logic with unit tests.

### Week 25 — Refactor & Modularization
  - Package: `week25_refactor_modularization`
  - Classes: `module-info.java` (optional), package-level refactors
  - Data: layered structure (`domain`, `app`, `ui`)
  - GUI: none
  - Deliverable: Cleaner boundaries and maintainability.

### Week 26 — Final Polish
  - Package: `week26_final_polish`
  - Classes: `Exporter`, `Importer`, `ReadmeGenerator` (optional)
  - GUI: theme tweaks, icons
  - Data: saved settings
  - Deliverable: Production-ready feel.

### Week 27 — Final Release
  - Package: `week27_final_release`
  - Classes: `ReleaseNotes`, `Packaging`
  - GUI: none
  - Data: final artifacts
  - Deliverable: Versioned release and portfolio.

## Working Notes
- Keep `Main.java` runnable; use it to manually test weekly increments.
- Add dependencies at the week they’re needed (JavaFX, Jackson, JUnit).
- Prefer records and sealed interfaces for domain models when you get to Week 12.
- Revisit earlier weeks to refactor with new features for deeper learning.

## Next Actions
- Fill week packages progressively using this PLAN.
- Use README for high-level orientation; expand PLAN with checklists as needed.