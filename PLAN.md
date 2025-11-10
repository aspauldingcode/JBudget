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
  - Micro-Exercises:
    - Implement `EnvironmentCheck.printInfo()` that prints Java version, Maven (if available), and project path.
    - Add one line in `Main` invoking `EnvironmentCheck.printInfo()` and confirm it runs.
    - Write a short README note about your setup and any issues found.

### Week 02 — Basics (types, variables, I/O)
  - Package: `week02_basics`
  - Classes: `InputDemo`, `MathDemo`, `StringDemo`
  - Data: primitives, `String`
  - GUI: none
  - Deliverable: Console demos for basic types and I/O.
  - Micro-Exercises:
    - Build `InputDemo` using `Scanner` to read an amount and a category, then echo them.
    - Create `MathDemo.sumAndAverage(int...)` and print results for a sample array.
    - Implement `StringDemo.formatCurrency(double)` that returns a currency-like string.

### Week 03 — Control Flow
  - Package: `week03_control_flow`
  - Classes: `ConsoleMenu`, `ValidationUtils`
  - Data: menu states (enums)
  - GUI: none
  - Deliverable: Prototype console menu to add/view dummy transactions.
  - Micro-Exercises:
    - Implement a loop-driven `ConsoleMenu` with options: Add, List, Quit.
    - Write `ValidationUtils.isPositiveAmount(double)` and `isNonEmpty(String)`; use them in the menu.
    - Simulate adding two hardcoded transactions and list them back.

### Week 04 — Methods & Recursion
  - Package: `week04_methods_recursion`
  - Classes: `DateUtils`, `AmountUtils`, `RecursionExamples`
  - Data: `LocalDate`
  - GUI: none
  - Deliverable: Utility methods used by later modules.
  - Micro-Exercises:
    - Implement `DateUtils.daysBetween(LocalDate a, LocalDate b)` and print for a sample range.
    - Implement `AmountUtils.roundToCents(BigDecimal)` and demonstrate on 3 inputs.
    - Write `RecursionExamples.factorial(int)` with base case and print factorial of 5.

### Week 05 — OOP Basics
  - Package: `week05_oop_basics`
  - Classes: `User`, `Account`
  - Data: `List<Account>` in `User`
  - GUI: none
  - Deliverable: Users can hold multiple accounts (no transactions yet).
  - Micro-Exercises:
    - Create `Account` with `deposit(double)` and `withdraw(double)` that update balance with validation.
    - Create `User` that aggregates accounts and a method to compute total balance.
    - In `Main`, create a user with two accounts and print the total.

### Week 06 — Encapsulation
  - Package: `week06_encapsulation`
  - Classes: `Money` (value object), `Category` (enum), `Budget`
  - Data: `Map<Category, Budget>`
  - GUI: none
  - Deliverable: Safe setters/getters; validated budget amounts.
  - Micro-Exercises:
    - Implement `Money` as a value type backed by cents (long) with `ofDollars(BigDecimal)` and `toBigDecimal()`.
    - Ensure `Budget` validates non-negative allocations and hides mutable internals.
    - Write a small demo that sets/get budgets per `Category` and prints totals.

### Week 07 — Inheritance & Polymorphism
  - Package: `week07_inheritance_polymorphism`
  - Classes: `Transaction` (abstract/base), `Income`, `Expense`, `Transfer`
  - Data: `List<Transaction>` per `Account`
  - GUI: none
  - Deliverable: Polymorphic transaction hierarchy (classic OOP).
  - Micro-Exercises:
    - Define abstract `Transaction` with common fields (date, amount, memo) and `apply(Account)`.
    - Implement `Income`, `Expense`, `Transfer` with specialized `apply` logic.
    - Create a list of mixed transactions and iteratively apply to an account; print final balance.

### Week 08 — Collections
  - Package: `week08_collections`
  - Classes: `TransactionRepository`, `InMemoryDatabase`
  - Data: `Map<String, Account>`, `List<Transaction>`
  - GUI: none
  - Deliverable: Efficient storage/retrieval patterns with collections.
  - Micro-Exercises:
    - Implement `TransactionRepository` with `add`, `findByAccount(String)`, `findByCategory(Category)`.
    - Build `InMemoryDatabase` storing accounts and transactions using `Map`/`List`.
    - Demonstrate two queries and print results.

### Week 09 — Generics
  - Package: `week09_generics`
  - Classes: `Result<T>`, `Repository<TId, TEntity>` (interfaces)
  - Data: typed repositories
  - GUI: none
  - Deliverable: Reusable generic abstractions.
  - Micro-Exercises:
    - Implement `Result<T>` with `success(T)` and `failure(String)`; add `map` and `flatMap`.
    - Define `Repository<TId, TEntity>` and implement `AccountRepository` using generics.
    - Show `Result<List<Transaction>>` returned from a query.

### Week 10 — Lambdas
  - Package: `week10_lambdas`
  - Classes: `TransactionFilter` (functional interface), `Callbacks`
  - Data: predicates and comparators
  - GUI: none
  - Deliverable: Lambda-powered filtering and sorting.
  - Micro-Exercises:
    - Define `TransactionFilter` and compose two predicates (e.g., amount > X and category == Y).
    - Sort transactions by date, then by amount using `Comparator` and print the first 3.
    - Implement a simple callback that runs after filtering to print a summary.

### Week 11 — Streams & Optional
  - Package: `week11_streams_optional`
  - Classes: `ReportService`, `Summary`
  - Data: stream pipelines, `Optional<Budget>`
  - GUI: none
  - Deliverable: Monthly/category summaries and aggregations.
  - Micro-Exercises:
    - Implement `ReportService.monthlySpendByCategory(List<Transaction>)` using streams.
    - Use `Optional<Budget>` for `findBudget(Category)`; demonstrate `orElse` and `orElseThrow`.
    - Build a `Summary` from a stream reduction and print top categories.

### Week 12 — Records & Sealed Types
  - Package: `week12_records_sealed`
  - Records: `IncomeRecord`, `ExpenseRecord`, `TransferRecord`
  - Sealed: `sealed interface TxRecord permits IncomeRecord, ExpenseRecord, TransferRecord`
  - Data: immutable transaction snapshots
  - GUI: none
  - Deliverable: Modern immutable models alongside classic OOP types.
  - Micro-Exercises:
    - Define the `TxRecord` sealed interface and the three record implementations.
    - Write a converter from `Transaction` to `TxRecord` and back where applicable.
    - Use a `switch` on `TxRecord` type to format a line of output.

### Week 13 — Pattern Matching, Switch Expressions, Text Blocks
  - Package: `week13_pattern_matching_textblocks`
  - Classes: `Formatter`, `PatternMatchingExamples`
  - Data: text block templates
  - GUI: none
  - Deliverable: Pretty-printed reports using modern control flow.
  - Micro-Exercises:
    - Implement a `switch` expression over transaction types to produce a formatted string.
    - Create a multi-line text block template for a summary report and fill tokens.
    - Demonstrate pattern matching with `instanceof` or `switch` for `TxRecord` variants.

### Week 14 — File I/O
  - Package: `week14_file_io`
  - Classes: `CsvExporter`, `CsvImporter`
  - Data: CSV rows for accounts/transactions
  - GUI: none
  - Deliverable: Export/import basic data.
  - Micro-Exercises:
    - Implement `CsvExporter` writing two transactions to a `transactions.csv` using `Files.newBufferedWriter`.
    - Implement `CsvImporter` reading `transactions.csv` and reconstructing transactions.
    - Print the imported list to confirm round-trip.

### Week 15 — Serialization & JSON (Jackson)
  - Package: `week15_serialization_json`
  - Classes: `JsonStore`, `JsonMapper`
  - Data: JSON files; DTO records
  - GUI: none
  - Deliverable: Persist and restore app state.
  - Micro-Exercises:
    - Implement `JsonStore.save(AppState)` and `load()` using Jackson.
    - Create a simple DTO record for transactions and map from domain to DTO.
    - Save state, clear in-memory data, then load and print a confirmation.

### Week 16 — Threads & Executors
  - Package: `week16_threads_executors`
  - Classes: `TransactionSimulator`, `BackgroundTasks`
  - Data: thread-safe collections
  - GUI: none
  - Deliverable: Concurrent transaction simulation.
  - Micro-Exercises:
    - Start an `ExecutorService` and submit 5 tasks that append transactions to a thread-safe list.
    - Implement a `Callable<Summary>` that computes totals asynchronously and prints the result.
    - Shut down the executor cleanly.

### Week 17 — Structured Concurrency
  - Package: `week17_structured_concurrency`
  - Classes: `TasksOrchestrator`
  - Data: scoped tasks
  - GUI: none
  - Deliverable: Clean orchestration of background jobs.
  - Micro-Exercises:
    - Orchestrate two tasks (fetch rates, compute report) with `CompletableFuture` or `StructuredTaskScope` if enabled.
    - Combine results and handle timeouts or failures gracefully.
    - Print a final summary when both tasks complete.

### Week 18 — JavaFX Basics
  - Package: `week18_javafx_basics`
  - GUI: `MainWindow`, layout panes, basic controls
  - Classes: `AppLauncher` (JavaFX), `ViewModel` stubs
  - Data: observable lists
  - Deliverable: GUI skeleton launches.
  - Micro-Exercises:
    - Create a `MainWindow` with a button and a list view bound to sample data.
    - Wire the button to append an item to the list.
    - Verify the app launches without errors.

### Week 19 — JavaFX Events
  - Package: `week19_javafx_events`
  - GUI: forms to add transactions/accounts
  - Classes: `EventHandlers`, `FormValidators`
  - Data: bound properties
  - Deliverable: Interactive forms wired to view models.
  - Micro-Exercises:
    - Build a simple form with text fields for amount and memo; add and clear actions.
    - Implement validation bindings to disable submit until inputs are valid.
    - Show a confirmation label when a transaction is added.

### Week 20 — JavaFX Tables & Charts
  - Package: `week20_javafx_tables_charts`
  - GUI: `TransactionsTable`, `CategoryChart`
  - Classes: `TableAdapters`, `ChartSeriesBuilder`
  - Data: observable table models
  - Deliverable: Visual summaries and lists.
  - Micro-Exercises:
    - Populate a `TableView<Transaction>` and enable sorting by amount/date.
    - Build a `PieChart` or `BarChart` summarizing spend per category.
    - Add a toggle to switch between table and chart views.

### Week 21 — GUI Integration
  - Package: `week21_gui_integration`
  - GUI: connect views to services (`ReportService`, `JsonStore`)
  - Classes: `Controllers`, `Bindings`
  - Data: application state model
  - Deliverable: Functional end-to-end UI.
  - Micro-Exercises:
    - Wire save/load buttons to `JsonStore` and confirm round-trip.
    - Bind a summary label to `ReportService` output and refresh on changes.
    - Hook up form submission to update the table and chart.

### Week 22 — HttpClient
  - Package: `week22_httpclient`
  - Classes: `ExchangeRateClient`
  - Data: remote JSON parsing
  - GUI: optional rates widget
  - Deliverable: External data fetch.
  - Micro-Exercises:
    - Use `HttpClient` to GET `https://api.exchangerate.host/latest?base=USD` and parse a couple of fields.
    - Expose a method `convert(BigDecimal amount, String currency)` using the fetched rates.
    - Print a sample conversion.

### Week 23 — Networking Integration
  - Package: `week23_network_integration`
  - Classes: `SyncService`, `RateApplier`
  - Data: merged state
  - GUI: refresh controls
  - Deliverable: Remote data affects budgets and reports.
  - Micro-Exercises:
    - Implement `SyncService.refreshRates()` and apply to existing budgets.
    - Update the UI to show last sync time and a refresh button.
    - Print a before/after comparison for one category.

### Week 24 — Testing (JUnit)
  - Package: `week24_testing_junit`
  - Classes: `BudgetTests`, `TransactionTests`, `ReportTests`
  - Data: test fixtures
  - GUI: none
  - Deliverable: Reliable core logic with unit tests.
  - Micro-Exercises:
    - Write `Money` arithmetic tests (add, subtract, round) using JUnit 5.
    - Test `Transaction.apply` for `Income`, `Expense`, `Transfer` with fixtures.
    - Test `ReportService.monthlySpendByCategory` with a small dataset.

### Week 25 — Refactor & Modularization
  - Package: `week25_refactor_modularization`
  - Classes: `module-info.java` (optional), package-level refactors
  - Data: layered structure (`domain`, `app`, `ui`)
  - GUI: none
  - Deliverable: Cleaner boundaries and maintainability.
  - Micro-Exercises:
    - Move classes into `domain`, `app`, `ui` packages; fix imports.
    - Optionally create `module-info.java` and declare exports/opens.
    - Identify one cyclic dependency and break it.

### Week 26 — Final Polish
  - Package: `week26_final_polish`
  - Classes: `Exporter`, `Importer`, `ReadmeGenerator` (optional)
  - GUI: theme tweaks, icons
  - Data: saved settings
  - Deliverable: Production-ready feel.
  - Micro-Exercises:
    - Add an app icon or small CSS tweak to improve UI.
    - Implement a quick export/import command from the UI and verify.
    - Generate a mini README section or a release note snippet programmatically.

### Week 27 — Final Release
  - Package: `week27_final_release`
  - Classes: `ReleaseNotes`, `Packaging`
  - GUI: none
  - Data: final artifacts
  - Deliverable: Versioned release and portfolio.
  - Micro-Exercises:
    - Draft `ReleaseNotes` with highlights and known limitations.
    - Tag the release and run packaging; confirm the runnable JAR.
    - Attach a screenshot/GIF of the UI (if applicable) to the release.

## Working Notes
- Keep `Main.java` runnable; use it to manually test weekly increments.
- Add dependencies at the week they’re needed (JavaFX, Jackson, JUnit).
- Prefer records and sealed interfaces for domain models when you get to Week 12.
- Revisit earlier weeks to refactor with new features for deeper learning.

### Packaging & Release (IntelliJ IDEA Community)
- Configure JDK: File > Project Structure > Project SDK set to JDK 25; set Language level to 25.
- Build the JAR: open the Maven tool window (View > Tool Windows > Maven), expand Lifecycle, run `package`. This produces `target/JBudget-1.0-SNAPSHOT.jar`.
- Runnable JAR: the manifest is configured (Main-Class `com.aspauldingcode.Main`), so you can run `java -jar target/JBudget-1.0-SNAPSHOT.jar` from the IDE Terminal.
- Tag the week: VCS > Git > Tag… create `week-NN` (e.g., `week-10`) and then VCS > Git > Push.
- Create a release: in the IDE Terminal run `gh release create week-NN target/JBudget-1.0-SNAPSHOT.jar --title "Week NN — Title" --notes "Plan Link: https://github.com/aspauldingcode/JBudget/blob/master/PLAN.md#week-NN--<anchor>"`. Alternatively, create a release on GitHub and upload the JAR.
- Optional naming: `cp target/JBudget-1.0-SNAPSHOT.jar target/JBudget-week-NN.jar` and attach the week-named JAR.
- Release notes: include 2–5 bullets of highlights (features, tests, screenshots if UI).

## Learning Plan

How to study effectively without relying on LLMs:
- Start with official docs first, then tutorials, then practice tasks.
- Take notes and write small, runnable examples for every concept.
- Build micro-exercises each week that align with the week’s deliverable.
- Revisit earlier code regularly to refactor with newer features.
- Prefer reading and API exploration over passive watching; use videos for reinforcement.

Core references
- JDK 25 Documentation (API): `https://docs.oracle.com/en/java/javase/25/docs/api/`
- Java Language Specification (SE 25): `https://docs.oracle.com/javase/specs/jls/se25/html/`
- OpenJDK JEP Index: `https://openjdk.org/jeps/`
- W3Schools Java: `https://www.w3schools.com/java/`
- GeeksforGeeks Java: `https://www.geeksforgeeks.org/java/`
- Baeldung Java: `https://www.baeldung.com/java-tutorial`
- OpenJFX Docs: `https://openjfx.io/openjfx-docs/`
- JUnit 5 User Guide: `https://junit.org/junit5/docs/current/user-guide/`

Weekly study links
- Week 01 — Setup
  - JDK Install (Oracle): `https://www.oracle.com/java/technologies/downloads/`
  - IntelliJ IDEA Community Setup: `https://www.jetbrains.com/help/idea/installation-guide.html`
  - Maven Basics: `https://maven.apache.org/guides/getting-started/`

- Week 02 — Basics, Types, Variables, IO
  - W3Schools Java Basics: `https://www.w3schools.com/java/java_intro.asp`
  - GeeksforGeeks Basics: `https://www.geeksforgeeks.org/java-programming-basics/`
  - Standard IO: `https://docs.oracle.com/en/java/javase/25/docs/api/java.base/java/io/package-summary.html`

- Week 03 — Control Flow
  - If/Switch/Loops (GfG): `https://www.geeksforgeeks.org/decision-making-java-if-else-switch/`
  - Switch Expressions (JEP 361): `https://openjdk.org/jeps/361`

- Week 04 — Methods & Recursion
  - Methods (W3Schools): `https://www.w3schools.com/java/java_methods.asp`
  - Recursion (GfG): `https://www.geeksforgeeks.org/recursion/`

- Week 05 — OOP Basics
  - Classes/Objects (Oracle): `https://docs.oracle.com/javase/tutorial/java/concepts/`
  - equals/hashCode (Baeldung): `https://www.baeldung.com/java-equals-hashcode-contract`

- Week 06 — Encapsulation
  - Access Modifiers (W3Schools): `https://www.w3schools.com/java/java_modifiers.asp`
  - Immutability (Baeldung): `https://www.baeldung.com/java-immutable-objects`

- Week 07 — Inheritance & Polymorphism
  - Inheritance (W3Schools): `https://www.w3schools.com/java/java_inheritance.asp`
  - Polymorphism (GfG): `https://www.geeksforgeeks.org/polymorphism-in-java/`

- Week 08 — Collections
  - Collections Framework (Oracle): `https://docs.oracle.com/en/java/javase/25/docs/api/java.base/java/util/Collections.html`
  - List/Set/Map (Baeldung): `https://www.baeldung.com/java-collections`

- Week 09 — Generics
  - Generics Guide (Oracle): `https://docs.oracle.com/javase/tutorial/java/generics/index.html`
  - Wildcards (Baeldung): `https://www.baeldung.com/java-generics`

- Week 10 — Lambdas
  - Functional Interfaces: `https://docs.oracle.com/en/java/javase/25/docs/api/java.base/java/util/function/package-summary.html`
  - Lambdas (Baeldung): `https://www.baeldung.com/java-8-lambda-expressions-tips`

- Week 11 — Streams & Optional
  - Streams API: `https://docs.oracle.com/en/java/javase/25/docs/api/java.base/java/util/stream/Stream.html`
  - Optional: `https://docs.oracle.com/en/java/javase/25/docs/api/java.base/java/util/Optional.html`
  - Streams (Baeldung): `https://www.baeldung.com/java-8-streams`

- Week 12 — Records & Sealed Types
  - Records (JLS §8.10): `https://docs.oracle.com/javase/specs/jls/se25/html/jls-8.html#jls-8.10`
  - Sealed Classes (JEP 409): `https://openjdk.org/jeps/409`

- Week 13 — Pattern Matching, Switch Expressions, Text Blocks
  - Pattern Matching (JEP 432): `https://openjdk.org/jeps/432`
  - Switch Expressions (JEP 361): `https://openjdk.org/jeps/361`
  - Text Blocks (JEP 378): `https://openjdk.org/jeps/378`

- Week 14 — File IO
  - NIO.2 Files/Path: `https://docs.oracle.com/en/java/javase/25/docs/api/java.base/java/nio/file/Files.html`
  - File IO (Baeldung): `https://www.baeldung.com/java-nio-2-file-api`

- Week 15 — Serialization & JSON
  - Jackson ObjectMapper: `https://github.com/FasterXML/jackson`
  - Jackson Guide (Baeldung): `https://www.baeldung.com/jackson`

- Week 16 — Threads & Executors
  - Executors: `https://docs.oracle.com/en/java/javase/25/docs/api/java.base/java/util/concurrent/ExecutorService.html`
  - Concurrency (Baeldung): `https://www.baeldung.com/java-concurrency`

- Week 17 — Structured Concurrency
  - Structured Concurrency (JEP 453): `https://openjdk.org/jeps/453`
  - StructuredTaskScope (preview docs may vary): `https://openjdk.org/jeps/428`

- Week 18 — JavaFX Basics
  - OpenJFX Getting Started: `https://openjfx.io/openjfx-docs/`
  - Tutorials (TutorialsEU/YouTube): `https://www.youtube.com/results?search_query=javafx+tutorial`

- Week 19 — JavaFX Events
  - Event Handling: `https://openjfx.io/javadoc/21/javafx.graphics/javafx/event/Event.html`
  - Controls (GfG overview): `https://www.geeksforgeeks.org/javafx-introduction/`

- Week 20 — JavaFX Tables & Charts
  - TableView: `https://openjfx.io/javadoc/21/javafx.controls/javafx/scene/control/TableView.html`
  - Charts: `https://openjfx.io/javadoc/21/javafx.controls/javafx/scene/chart/package-summary.html`

- Week 21 — GUI Integration
  - MVC & Controllers (Baeldung FX guide): `https://www.baeldung.com/javafx`
  - Bindings/Properties: `https://openjfx.io/javadoc/21/javafx.base/javafx/beans/property/package-summary.html`

- Week 22 — HttpClient
  - HttpClient: `https://docs.oracle.com/en/java/javase/25/docs/api/java.net.http/java/net/http/HttpClient.html`
  - HttpClient Guide (Baeldung): `https://www.baeldung.com/java-9-http-client`

- Week 23 — Networking Integration
  - JSON Parsing + Apply data (Jackson + domain): `https://www.baeldung.com/jackson`
  - Error handling (GfG): `https://www.geeksforgeeks.org/exception-handling-in-java/`

- Week 24 — Testing (JUnit)
  - JUnit 5 User Guide: `https://junit.org/junit5/docs/current/user-guide/`
  - AssertJ: `https://assertj.github.io/doc/`

- Week 25 — Refactor & Modularization
  - Java Modules: `https://openjdk.org/projects/jigsaw/`
  - module-info basics (Baeldung): `https://www.baeldung.com/java-9-modularity`

- Week 26 — Final Polish
  - Javadoc: `https://docs.oracle.com/en/java/javase/25/docs/specs/javadoc/doc-comment-spec.html`
  - Packaging tips: `https://maven.apache.org/plugins/`

- Week 27 — Final Release
  - Release notes best practices (GitHub): `https://docs.github.com/en/repositories/releasing-projects-on-github`
  - Versioning: `https://semver.org/`

## Next Actions
- Fill week packages progressively using this PLAN.
- Use README for high-level orientation; expand PLAN with checklists as needed.