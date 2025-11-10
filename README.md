# JBudget — Personal Finance Budgeting App (Java 25)

JBudget is a learning-first personal finance app designed to help you master modern Java by building something useful. The project progresses week-by-week, introducing core language concepts, libraries, and patterns while implementing real app features like accounts, budgets, transactions, reports, persistence, GUI, and optional networking.

Developed by Alex Spaulding (`aspauldingcode`) as a self-led project to learn programming in Java. The long-term goal is to learn and implement every major Java feature while applying solid OOP, data structures, and clean architecture. Knowledge gained here supports broader computer science learning and strengthens practical engineering skills.

## Goals
- Learn Java fundamentals through a practical app.
- Incrementally implement features across 6 months.
- Use modern Java (25) features and good practices.
- Keep code modular with clear weekly milestones.

## Tech Stack
- JDK: OpenJDK 25
- Build: Maven
- IDE: IntelliJ IDEA Community
- Optional: JavaFX (GUI), Jackson (JSON), JUnit (testing)

## Structure
Source layout follows per-week packages so you can focus on the topic of the week without being overwhelmed:

```
src/main/java/com/aspauldingcode/
  week01_setup/
  week02_basics/
  week03_control_flow/
  week04_methods_recursion/
  week05_oop_basics/
  week06_encapsulation/
  week07_inheritance_polymorphism/
  week08_collections/
  week09_generics/
  week10_lambdas/
  week11_streams_optional/
  week12_records_sealed/
  week13_pattern_matching_textblocks/
  week14_file_io/
  week15_serialization_json/
  week16_threads_executors/
  week17_structured_concurrency/
  week18_javafx_basics/
  week19_javafx_events/
  week20_javafx_tables_charts/
  week21_gui_integration/
  week22_httpclient/
  week23_network_integration/
  week24_testing_junit/
  week25_refactor_modularization/
  week26_final_polish/
  week27_final_release/
```

Each package contains placeholder classes for weekly exercises and app modules. Implementation will be added as you progress with the PLAN.

## Running
- IntelliJ: Open the project, select the run config `JBudget (Main)`, click Run.
- Maven: `mvn clean compile` to build; `mvn exec:java` can be added later for CLI runs.

## JDK (Homebrew) Setup
- This project uses JDK 25 installed via Homebrew. If tools don’t detect it, create a user-level symlink so macOS Java tools find it:
  - `ln -sfn /opt/homebrew/opt/openjdk/libexec/openjdk.jdk /Users/$USER/Library/Java/JavaVirtualMachines/openjdk-25.jdk`
- Optionally set environment variables for terminal builds:
  - `export JAVA_HOME=/opt/homebrew/opt/openjdk/libexec/openjdk.jdk/Contents/Home`
  - `export PATH="$JAVA_HOME/bin:$PATH"`
- In IntelliJ, set Project SDK to the linked JDK 25.

## License
- MIT License

## Notes
- Preview features can be enabled later if needed.
- JavaFX and other dependencies will be introduced in the week they’re used.