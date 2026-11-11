# Defense guide — English explanations

## Shared demo (90 seconds)

"Our project is Study Sprint, a Java Swing study planner for students. It has three domain entities: StudyPlan, StudyTask and StudySession. The user creates and configures tasks, chooses an ordering algorithm, generates a schedule and exports a report. Plans are saved locally. We implemented eight integrated patterns."

## Erasyl — Builder and Strategy

**Builder:** "StudyPlanBuilder creates a StudyPlan in steps with a name, strategy, breaks and tips. It avoids an unwieldy constructor. The downside is one more class."

**Strategy:** "ScheduleStrategy defines arrange(). PriorityStrategy orders unfinished tasks by priority, ShortestStrategy by time. New algorithms can be added without changing task models. The downside is having more classes."

Practice: add LongestStrategy, add it to StudyPlan validation, scheduler selection and UI.

## Arsen — Factory Method and Decorator

**Factory Method:** "TaskCreator delegates concrete creation to ReadingTaskCreator or PracticeTaskCreator. Both return StudyTask with different study tips. New task types require a new subclass."

**Decorator:** "BasicSessionText is extended by BreakDecorator and TipDecorator. They share SessionText and can be combined independently. Too many nested decorators are harder to debug."

Practice: implement LongBreakDecorator that adds ten minutes.

## Abylaikhan — Observer and Facade

**Observer:** "StudyFacade calls PlanObserver when data changes. ActivityHistory records the message and the GUI automatically refreshes. A failing observer could interfere with notification."

**Facade:** "The GUI calls StudyFacade instead of directly managing persistence, scheduling, factories and reporting. It simplifies usage, but can become a large class."

Practice: create ConsoleObserver implements PlanObserver and register it.

## Adilzhan — Adapter and Bridge

**Adapter:** "OldCsvReader gives arrays of strings. LegacyCsvAdapter converts them to StudyTask objects and implements TaskImporter. It reuses old code. The basic CSV reader cannot handle quoted commas."

**Bridge:** "StudyReport is the abstraction for SummaryReport and DetailedReport; ReportFormat is the implementation for PlainTextFormat and HtmlFormat. Types and formats vary independently."

Practice: implement MarkdownFormat implements ReportFormat and expose it in the GUI.

## Questions for all members

- Why eight patterns? Six distinct are required, and four people need at least two independently implemented patterns each.
- Where is the separation? UI, model, services/patterns and storage have distinct directories.
- Where are values checked? StudyTask, StudyPlan and the importer.
- Where are plans saved? PlanRepository in data/plans.txt.
- What is the main journey? Create/configure/generate/view/export.
- What would be improved? Richer scheduling, date reminders, multi-user sharing, and GUI automation.

Practice explaining and modifying the code yourself, rather than memorizing these scripts alone.
