# Sample Reporting

Sample Reporting is an Oracle APEX sample application that demonstrates native APEX reporting features and common SQL reporting techniques. It uses a small project/task data set, the classic EMP/DEPT sample data, and a PL/SQL package used by one of the advanced SQL examples.

## Requirements and Explanation

This is an Oracle APEX 26.1 application tested on an Oracle Database 26ai environment.

The export files in this repository are written in APEXlang format, not as a single traditional SQL export. The application is split across `application.apx`, `pages/`, `shared-components/`, `workspace-components/`, and `supporting-objects/`.

## Installation Guide

To install the application in your own environment:

1. Use SQLcl with APEXlang support to import the application from this folder.
2. Or zip the full application directory and import it through the Oracle APEX Application Builder import feature.
3. During import, install the supporting objects when prompted so the demo tables, sample data, and PL/SQL package are created.

The application includes supporting object installation, upgrade, and deinstallation scripts.

## What Does the App Do?

The app is a reporting showcase for Oracle APEX. It demonstrates how to build and configure interactive reports, interactive grids, classic reports, cards, faceted search, drill-down reports, report linking, format masks, highlighting, bind-variable filtering, and SQL-driven report examples.

The home page presents the main reporting areas:

- **Interactive Report**: Demonstrates end-user report customization, searching, sorting, filtering, downloads, detail view, saved reports, chart/group-by/pivot views, report highlighting, and drill-through editing.
- **Interactive Grid**: Demonstrates editable grid reporting with add, update, delete, save, search, actions menu, downloads, and saved grid views.
- **Classic Report**: Demonstrates tabular report output with page-item filtering through bind variables.
- **Faceted Search**: Demonstrates a faceted search region filtering a classic report by search text, project, assigned user, status, cost range, and budget range.
- **Cards**: Demonstrates a cards region for presenting project/task information in compact blocks.
- **Use Cases**: Demonstrates practical APEX reporting techniques.
- **SQL Examples**: Demonstrates SQL syntax useful in reports.
- **Analytic Functions**: Demonstrates analytic SQL functions in report pages.

### Report Use Cases

The Use Cases area includes examples for:

- Drill-down links from interactive reports and interactive grids.
- Built-in interactive report highlighting.
- Calling the Interactive Report Query API and using the current report query to drive another visualization.
- Linking to interactive reports and grids with reset, clear, saved report, and filter parameters.
- Filtering classic reports from page items and side-bar controls.
- Bind variables in report SQL.
- Column format masks for dates, numbers, currency, and computed values.
- Non-tabular classic report templates, including comment-bubble style output.
- CSS-based custom buttons in report cells.
- Reporting from Oracle APEX collections.

### SQL and Analytic Examples

The SQL Examples and Analytic Functions areas include report pages for:

- `CASE` expressions.
- `CONNECT BY` hierarchy queries.
- `GROUP BY` aggregate reporting.
- Inline views.
- Pipelined table functions.
- `PIVOT`.
- Regular expressions.
- `SOUNDEX`.
- String functions such as `SUBSTR`, `INSTR`, `NVL`, `NVL2`, `COALESCE`, `REPLACE`, and `TRIM`.
- `LEAD` and `LAG`.
- `LISTAGG`.
- `RANK` and `DENSE_RANK`.
- `RATIO_TO_REPORT`.
- `ROW_NUMBER`.
- Top-N queries.

### Administration

The Administration section includes:

- **Manage Sample Data**: Recreates or removes the sample data used by the reporting examples.
- **Application Theme Style**: Lets administrators change the application UI theme style.

## Page Map

| Page | Name | Purpose |
| ---: | --- | --- |
| 1 | Interactive Report | Main interactive report over project/task data. |
| 2 | Maintain Project | Form page used to edit project/task rows. |
| 3 | Classic Report | Classic report example with page-item filtering. |
| 4 | Manage Sample Data | Administrative data reset/removal page. |
| 5 | Filtering | Classic report filtered by side-bar controls. |
| 6 | Drill Down IR | Interactive report with drill-down column links. |
| 7 | Highlighting | Interactive report highlighting example. |
| 8 | Format Masks | Report formatting examples. |
| 9 | Use Cases | Card/list entry point for reporting use cases. |
| 10 | Home | Main entry page for report example categories. |
| 11 | Interactive Report Query API | Uses APEX runtime APIs around interactive report filters and query text. |
| 12 | Custom Buttons | Interactive report with button-like report cells. |
| 13 | Non-Tabular Templates | Classic report using a custom non-tabular template. |
| 14 | Help | Application help page. |
| 15 | Bind Variables | Interactive report filtered by APEX page item bind variables. |
| 17 | Interactive Grid | Editable interactive grid over project/task data. |
| 18 | Linking to Interactive Reports | Examples for linking to reports, saved reports, and filtered report states. |
| 19 | CASE Statement | SQL `CASE` expression report example. |
| 20 | Top N Queries | Top-N SQL report example. |
| 21 | Analytic Function Examples | Entry point for analytic SQL examples. |
| 22 | Inline Views | Inline view SQL report example. |
| 23 | Group By Clause | Aggregate reporting with `GROUP BY`. |
| 24 | LEAD and LAG | Analytic `LEAD` and `LAG` report example. |
| 25 | Pivot Syntax | SQL `PIVOT` report example. |
| 26 | Connect By | Hierarchical query report example. |
| 27 | String Functions | String function examples selected through a list. |
| 28 | Regular Expressions | Regular expression SQL report example. |
| 29 | Soundex | Phonetic matching example. |
| 30 | LISTAGG | String aggregation example. |
| 31 | RANK and DENSE_RANK | Analytic ranking example. |
| 32 | ROW_NUMBER | Analytic row numbering example. |
| 33 | RATIO_TO_REPORT | Analytic ratio example. |
| 34 | Application Theme Style | Theme style administration page. |
| 35 | Pipelined Functions | Report based on a PL/SQL pipelined table function. |
| 36 | Administration | Administration menu page. |
| 37 | Linking to Interactive Grids | Examples for linking to interactive grid report states. |
| 38 | Report from Collection | Report over an Oracle APEX collection. |
| 39 | SQL Examples | Entry point for SQL syntax examples. |
| 40 | Drill Down IG | Interactive grid with drill-down column links. |
| 41 | Cards | Cards-region report example. |
| 42 | Faceted Search | Faceted filtering over project/task data. |
| 101 | Login | Application sign-in page. |

## Supporting Objects

The supporting objects create and manage the sample schema objects used by the app.

### Installed Objects

- `EBA_DEMO_IR_PROJECTS`: Main project/task table used by the report, grid, cards, and faceted search examples.
- `BIU_EBA_DEMO_IR_PROJECTS`: Trigger that generates IDs, increments `ROW_VERSION_NUMBER`, and validates that `START_DATE` is not after `END_DATE`.
- `EBA_DEMO_IR_DEPT`: Department sample table.
- `EBA_DEMO_IR_EMP`: Employee sample table with a self-referencing manager foreign key.
- `EBA_DEMO_IR_DATA`: Procedure that reloads project/task and EMP/DEPT sample data.
- `EBA_DEMO_IR_PKG`: PL/SQL package containing pipelined functions used to report page-link reference counts inside the current APEX application.

### Install Scripts

- `set-plscope-settings.sql`
- `create-table.sql`
- `emp-and-dept-tables.sql`
- `pipelined-function-package.sql`
- `load-data.sql`

### Upgrade Scripts

- `create-dept-table.sql`
- `create-emp-table.sql`
- `update-data-script.sql`
- `refresh-data.sql`
- `pipelined-function-package.sql`
- `drop-old-objects.sql`

### Deinstall

The supporting object definition references `deinstall-script.sql`, which removes the objects created for the sample application.
