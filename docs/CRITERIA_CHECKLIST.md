# Final Project assessment checklist

Source: FINAL PROJECT — Build Something People Can Use (Software Design Patterns).

## Functional requirements

- [x] StudyPlan, StudyTask, StudySession: three related entities.
- [x] Five or more user scenarios: create/select plan, add task, edit, mark done, configure, generate, import, export.
- [x] Create, view, edit and delete/cancel.
- [x] Interchangeable behavior: PriorityStrategy, ShortestStrategy.
- [x] Observer event reaction: history and GUI update.
- [x] Persistent local storage after restart: PlanRepository.
- [x] Final saved/exported output: TXT and HTML reports.
- [x] Input validation and error handling: empty fields, invalid duration/priority, empty schedule, invalid CSV.
- [x] Sample data on first launch; example CSV file.

## Design patterns

- [x] 8 distinct patterns implemented (minimum 6): Builder, Factory Method, Strategy, Decorator, Observer, Facade, Adapter, Bridge.
- [x] At least one creational, structural and behavioral pattern.
- [x] Patterns are integrated into the live GUI workflow.
- [ ] Students must independently revise/implement at least two patterns each, demonstrate and explain them.
- [ ] Final PDF should include pattern problem/classes/demo/responsible-student table based on actual contributions.

## Interface and architecture

- [x] Java Swing desktop GUI, connected to real Java logic.
- [x] Browsing, editing, configuration, full journey, output and errors.
- [x] Separate ui, model, service/patterns and storage packages.

## Tests

- [x] 22 automated business logic checks with `StudySprintTests`.
- [x] More than 8 documented test scenarios with expected and actual outcomes.
- [x] Tested switching strategy, observer, persistence and at least 3 invalid cases.
- [x] GitHub Actions checks compilation and test runner on pushes.
- [ ] Each student should manually test GUI on their own laptop.

## Delivery and defense

- [x] GitHub repository with source, README, launch instructions and diagrams in Mermaid text.
- [ ] Include final PDF report and exported PNGs in Moodle submission.
- [ ] Class + sequence UML must be included in the final PDF.
- [ ] Show genuine Week 1–3 progress to instructor as required, do not invent meeting evidence.
- [ ] Each member demonstrates patterns and makes a small instructor-requested code change.
- [ ] Truthfully disclose AI/external tools under course rules.

## Grades

Functionality 20, patterns 30, architecture/readability 10, UI 5, documentation/testing/Git 5, individual defense 30. Total 100. A score of 95+ is not guaranteed.
