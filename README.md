# To Do List — QA Test Package

This folder contains the full QA deliverable set for manual testing of the To Do List web application (`todolist.james.am`), organized around the CRUD model (Create, Read, Update, Delete).

# Project in trello

👉 **[To-Do List Web App QA - Trello Board](https://trello.com/invite/b/6a8477ce464e4b0d4b1d9d1c/ATTIfe02a3d2dfc5c5e0fa9380d09cef64f1B34D50AB/to-do-list-web-app)** *(Read-Only / Observer Access)*

## Contents

| File | Description |
|---|---|
| [`Test_Summary_Report.md`](Test_Summary_Report.md) | High-level summary of the testing cycle — scope, execution stats, defect summary, coverage assessment, and release recommendation. **Start here.** |
| [`Todo_App_Test_Cases.xlsx`](Todo_App_Test_Cases.xlsx) | Full repository of 37 test scenarios, grouped by Module and Test Group, each with a Priority (High / Normal / Low) and Status. Includes a Summary sheet with live counts by group and priority. |
| [`Todo_App_Bug_Reports.md`](Todo_App_Bug_Reports.md) | Detailed defect reports (5 total) — each with steps to reproduce, expected result, actual result, and a screenshot. |
| [`screenshots/`](screenshots/) | Screenshot evidence referenced by the bug reports. |

## How these fit together

1. **`Test_Summary_Report.md`** gives the overall picture: how many scenarios were tested, how many defects were found, and whether the build is release-ready.
2. **`Todo_App_Test_Cases.xlsx`** is the source of truth for every scenario that was planned and executed, with priority ratings for triage.
3. **`Todo_App_Bug_Reports.md`** documents the defects found during execution in full detail, for developers to reproduce and fix.

## Defects at a glance

| # | Defect | Module | Severity |
|---|---|---|---|
| 1 | "Items left" counter shows one fewer than the actual number of active tasks | Read | High |
| 2 | Toggle-all icon requires two clicks to revert all tasks to active when all are completed | Update | Medium |
| 3 | Task display collapses multiple whitespace characters into a single space, while edit mode preserves them | Update | Low |
| 4 | Input placeholder contains a grammatical error ("need's" instead of "needs") | Create | Low |
| 5 | Input field does not fully clear after submitting input | Create | Low |
