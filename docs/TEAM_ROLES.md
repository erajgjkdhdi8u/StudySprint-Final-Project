# Study Sprint: team responsibilities

This is a suggested division of work. It does not claim that each student independently authored the code that was initially provided. Each person should review, implement genuine improvements, test and defend their patterns.

## 1. Erasyl: Builder and Strategy

Files: `StudyPlanBuilder.java`, `ScheduleStrategy.java`, `PriorityStrategy.java`, `ShortestStrategy.java`.
Responsibilities: plan creation and configuring algorithm choice. Demo both Priority first and Shortest first with tasks of different length and priority. Live-code practice: add a Longest first strategy and update UI/scheduler.

## 2. Arsen: Factory Method and Decorator

Files: `TaskCreator.java`, `ReadingTaskCreator.java`, `PracticeTaskCreator.java`, `TaskCreators.java`, `ReadingTask.java`, `PracticeTask.java`, `SessionText.java`, `BasicSessionText.java`, `BreakDecorator.java`, `TipDecorator.java`.
Responsibilities: task variants and optional tips/breaks. Demo Reading/Practice and adding/removing schedule decorations. Practice: implement a ten-minute break decorator or new task type.

## 3. Abylaikhan: Observer and Facade

Files: `PlanObserver.java`, `ActivityHistory.java`, `StudyFacade.java`; UI integration.
Responsibilities: event notifications, activity history and public methods connecting services. Demo changing data and observing Activity update. Practice: add a second observer that logs to console.

## 4. Adilzhan: Adapter and Bridge

Files: `TaskImporter.java`, `OldCsvReader.java`, `LegacyCsvAdapter.java`, `ReportFormat.java`, `PlainTextFormat.java`, `HtmlFormat.java`, `StudyReport.java`, `SummaryReport.java`, `DetailedReport.java`.
Responsibilities: CSV import and report output types. Demo importing the sample CSV and exporting Summary TXT / Detailed HTML. Practice: implement a Markdown report format.

## Shared work

All four must understand StudyPlan, StudyTask, StudySession, UI, validation, storage, tests and the full user journey. Each person should push real changes using their own account or open a PR, and explain limitations during defense.

See `docs/UML_CLASS.mmd` and `docs/UML_SEQUENCE.mmd` for diagrams, and `docs/AI_DISCLOSURE.md` for tool attribution.
