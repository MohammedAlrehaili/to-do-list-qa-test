# Test Summary Report

**Project:** To Do List Application (todolist.james.am)
**Prepared by:** Mohammed Abdullah Alrehaili
**Report Date:** August 19, 2026
**Test Type:** Manual Functional Testing (CRUD-based)
**Related Documents:** `Todo_App_Test_Cases.xlsx` (full test case repository), `Todo_App_Bug_Reports.md` (detailed defect reports)

---

## 1. Objective

This report summarizes the manual functional testing performed on the To Do List web application. Testing was organized around the CRUD model (Create, Read, Update, Delete) to validate that users can reliably add, view, edit, and remove tasks, and that supporting behaviors — filtering, the items counter, toggle-all, and bulk deletion — work as expected.

## 2. Scope

**In scope:**
- Task creation, including validation rules (empty/whitespace input, duplicates, special characters, Unicode, malicious input)
- Task viewing and filtering (All / Active / Completed), items counter accuracy, and data persistence
- Task editing (inline edit mode, save/cancel behavior) and status toggling (individual and toggle-all)
- Task deletion (individual delete, "Clear completed" bulk delete)

**Out of scope:**
- Cross-browser and mobile responsiveness testing (testing was performed in Chrome only)
- Performance, load, and accessibility testing
- Automated test scripting

## 3. Test Environment

| Item | Detail |
|---|---|
| Application URL | todolist.james.am |
| Browser | Google Chrome (desktop) |
| Test type | Manual, exploratory + scripted scenarios |
| Test case repository | `Todo_App_Test_Cases.xlsx` |

## 4. Test Execution Summary

| Metric | Count |
|---|---|
| Total test scenarios designed | 37 |
| Test scenarios executed | 37 |
| Defects found | 5 |
| Modules covered | Create, Read, Update, Delete |

### Scenarios by Module

| Module | Test Scenarios | High | Normal | Low |
|---|---|---|---|---|
| Create | 12 | 5 | 5 | 2 |
| Read | 8 | 7 | 0 | 1 |
| Update | 10 | 7 | 3 | 0 |
| Delete | 7 | 4 | 0 | 3 |
| **Total** | **37** | **24** | **9** | **4** |

*(Full scenario-level detail and priority ratings are in `Todo_App_Test_Cases.xlsx`.)*

## 5. Defect Summary

| # | Defect | Module | Severity |
|---|---|---|---|
| 1 | "Items left" counter shows one fewer than the actual number of active tasks | Read | High |
| 2 | Toggle-all icon requires two clicks to revert all tasks to active when all are completed | Update | Medium |
| 3 | Task display collapses multiple whitespace characters into a single space, while edit mode preserves them | Update | Low |
| 4 | Input placeholder contains a grammatical error ("need's" instead of "needs") | Create | Low |
| 5 | Input field does not fully clear after submitting input | Create | Low |

**Defect breakdown by severity:** 1 High · 1 Medium · 3 Low

*(Full steps to reproduce, expected/actual results, and screenshots for each defect are in `Todo_App_Bug_Reports.md`.)*

## 6. Test Coverage Assessment

- **Create:** Core add-task flow, validation rules, and edge-case input (Unicode, special characters, malicious input) were all covered. One defect found relates to post-submit input clearing.
- **Read:** Filtering and data persistence behaved correctly, but the items counter — a core piece of app state shown to the user on every screen — was found to be inaccurate. This is the most severe defect in this cycle.
- **Update:** Inline editing (save/cancel) worked as expected in all cases tested. The toggle-all control has a state-sync issue requiring a second click to fully revert task status.
- **Delete:** Individual and bulk ("Clear completed") deletion both worked correctly across all tested conditions, with no defects found in this module.

## 7. Risks and Known Issues

- The items counter defect (#1) directly affects the accuracy of information shown to the user on the main screen and should be prioritized for a fix.
- The toggle-all defect (#2) could confuse users who expect a single click to fully revert task states; while a workaround exists (click twice), this is not intuitive.
- Defects #3–#5 are cosmetic/display issues and do not block core task management functionality, but affect UI polish and data-display consistency.

## 8. Conclusion

Out of 37 test scenarios executed across the Create, Read, Update, and Delete flows, 5 defects were identified. The core task management functionality (adding, viewing, editing, and deleting tasks) is largely stable, with all Delete scenarios passing without issue. The most significant defect is the inaccurate items counter (High severity), which should be addressed before this build is considered release-ready. The remaining defects are lower severity and can be scheduled for a subsequent fix cycle.

**Recommendation:** Fix defects #1 and #2 before release; track #3–#5 as minor/cosmetic defects for a future sprint.
