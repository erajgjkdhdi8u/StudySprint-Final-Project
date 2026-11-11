# Test scenarios

Run `test.bat` on Windows or `./test.sh` on Linux/macOS. Tests are in `src/test/java/kz/studysprint/StudySprintTests.java`.

| # | Scenario | Input | Expected result |
|---|---|---|---|
| 1 | First launch | Empty data directory | Sample plan and three tasks |
| 2 | Create plan | Name: My tests | Plan created |
| 3 | Create different task types | Reading 60m, Practice 20m | Two types with distinct study tips |
| 4 | Switch ordering | Priority 5/1 and times 60/20 | Each strategy gives its intended order |
| 5 | Decorators | Enable breaks and tips | +10 minutes and tips shown |
| 6 | Observer | Generate schedule | History receives notification |
| 7 | Complete task | Mark unfinished task done | Completion saved; stale sessions cleared |
| 8 | Persistence | Restart using same file | Plan/tasks/settings retained |
| 9 | Reports | Detailed HTML/TXT | Proper output |
| 10 | Empty title | Blank title | Validation error |
| 11 | Invalid duration | 1 minute | Validation error |
| 12 | Invalid priority | Priority 8 | Validation error |
| 13 | Invalid plan name | Blank name | Validation error |
| 14 | Import CSV | Two valid rows | Two tasks created |
| 15 | Invalid CSV | Negative time | Error; no partial import |
| 16 | Edit/delete | Rename and delete task | Correct final state, persisted |

The test runner contains 22 assertions and prints each PASS line. See `docs/test_output.txt` for results recorded with the supplied project.

## Manual verification before defense

Launch the Swing GUI. Try plan creation, rename, deletion, task creation, editing, completion, selecting different strategies, importing CSV, previewing and saving reports. Restart the application to confirm persistence. Check error dialogs when no task is selected.
