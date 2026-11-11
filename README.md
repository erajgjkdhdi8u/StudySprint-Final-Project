# Study Sprint - Final Project

**Course:** Software Design Patterns  
**Team:** Erasyl, Arsen, Abylaikhan, Adilzhan  
**Language:** Java 17+, Swing GUI, no external dependencies.

## Purpose

Study Sprint helps a student create a study plan, add Reading/Practice tasks, choose scheduling options, generate a schedule, mark tasks as done, and save a TXT or HTML report. Plans are saved automatically. The first run creates an example plan.

Main entities: `StudyPlan`, `StudyTask`, and `StudySession`.

## Run on Windows with IntelliJ IDEA

1. Install JDK 17 or newer.
2. Open this repository folder in IntelliJ IDEA and set Project SDK.
3. Run `src/main/java/kz/studysprint/App.java` using `App.main()`.
4. Or open Command Prompt in the project folder and run `run.bat`.

Linux/macOS: run `chmod +x run.sh test.sh` then `./run.sh`. Maven is not needed.

## Tests

Run `test.bat` on Windows or `./test.sh` on Linux/macOS. You can also run `StudySprintTests.main()` in IntelliJ IDEA.

The test class checks 22 business cases, including two schedule strategies, storage across a restart, import/export, Observer reactions, Decorators, invalid input, creating/editing/deleting tasks and report formats.

## Demonstration

1. Start the app. The example plan `Exam preparation` has three tasks.
2. Create a plan with **New**, then add Reading and Practice tasks.
3. Edit a task and change its status using **Done / Undo**.
4. Select **Priority first** and **Generate schedule**.
5. Change to **Shortest first** and compare task ordering.
6. Enable optional breaks and study tips.
7. Open **Reports**, choose Detailed + HTML or Summary + TXT, preview and save.
8. Open **Activity** to see Observer notifications.
9. Restart the app and check the saved plans. Optionally import `samples/legacy_tasks.csv`.

Main journey: create/select a plan -> configure tasks and options -> generate -> view/export.

## Storage and input rules

Data is stored locally in `data/plans.txt`, which is ignored by Git. The sample plan appears if no saved file exists. To reset it, close the app and remove the `data` directory.

Task title and subject cannot be empty; minutes must be 5–300; priority must be 1–5. CSV format is `title,subject,minutes,priority,type` with type Reading or Practice. This simple reader does not support quoted commas in fields.

## Eight patterns

| Assigned student | Patterns | Classes |
|---|---|---|
| Erasyl | Builder, Strategy | StudyPlanBuilder, ScheduleStrategy, PriorityStrategy, ShortestStrategy |
| Arsen | Factory Method, Decorator | TaskCreator, ReadingTaskCreator, PracticeTaskCreator, BreakDecorator, TipDecorator |
| Abylaikhan | Observer, Facade | PlanObserver, ActivityHistory, StudyFacade |
| Adilzhan | Adapter, Bridge | LegacyCsvAdapter, OldCsvReader, StudyReport, ReportFormat, SummaryReport, DetailedReport |

These are **assigned responsibilities**, not claims of independently authored source code. Each team member must review, modify, test and be able to explain their own section on defense.

## Directory structure

- `src/main/java/kz/studysprint/model` - domain objects
- `patterns` - 8 design patterns
- `service` - schedule business logic
- `storage` - local persistence
- `ui` - Swing application window and forms
- `src/test` - automated business checks
- `samples` - input CSV
- `docs` - UML, test plan, team responsibilities, AI disclosure

## Limitations

Study Sprint is a single-user desktop app; it has no cloud sync or university integration. The CSV importer is intentionally simple. Changing tasks or scheduling options clears older generated sessions.

## Academic work and submission

The course requires a working GUI and at least six integrated design patterns, source ZIP, Git repository link, diagrams, test results, PDF report, and individual live defense. Everyone must demonstrate real contributions and understand the code.

This starter was developed with AI assistance. See `docs/AI_DISCLOSURE.md` and update the final report to accurately describe actual independent work. Do not fabricate contributors, commits, or dates.
