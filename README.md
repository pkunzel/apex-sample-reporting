# Sample Reporting

## Overview

Sample Reporting is an Oracle APEX sample application that demonstrates native APEX reporting capabilities and SQL reporting patterns. It uses project/task sample data, EMP/DEPT sample tables, cards, faceted search, classic reports, interactive reports, interactive grids, and PL/SQL pipelined functions to show common reporting techniques in a working app.

## Requirements and Explanation

This repository contains an Oracle APEX 26.1 application in APEXlang split-export format. The application definition is separated across `application.apx`, `pages/`, `shared-components/`, `workspace-components/`, and `supporting-objects/`.

To import and run the app, you need:

- Oracle APEX 26.1 or a compatible APEX environment.
- An Oracle Database schema where the supporting objects can be installed.
- SQLcl with APEXlang support, or an APEX import workflow that accepts a zipped split application export.
- Privileges to create tables, indexes, triggers, procedures, packages, types, and views in the parsing schema.

The application uses `mustNotBePublicUser` as the page-level authorization scheme across the exported pages.

## Installation Guide

1. Clone or download this repository.
2. Import the APEX application from this folder with SQLcl/APEXlang, or zip the full application directory and import it through Oracle APEX Application Builder.
3. During import, choose to install supporting objects when prompted.
4. Confirm that the install scripts create the demo tables, seed data, trigger, procedure, and PL/SQL package.
5. Run the application and sign in through the login page.

If the app was previously installed, the supporting-object upgrade flow can refresh data, create missing EMP/DEPT tables, rebuild the pipelined-function package, and remove obsolete package/type objects.

## What Does the App Do?

The app is a reporting showcase for Oracle APEX. It demonstrates:

- Interactive reports with searching, sorting, filtering, saved reports, charts, group-by views, pivot views, detail views, highlighting, download options, and drill-down links.
- Interactive grids with editable rows, grid actions, report state links, and drill-down examples.
- Classic reports with bind-variable filtering, format masks, custom templates, custom button-style cells, and collection-backed data.
- Cards and faceted search over the same project/task data.
- SQL examples for `CASE`, inline views, `GROUP BY`, `CONNECT BY`, `PIVOT`, regular expressions, string functions, `SOUNDEX`, and top-N queries.
- Analytic SQL examples for `LEAD`, `LAG`, `LISTAGG`, `RANK`, `DENSE_RANK`, `ROW_NUMBER`, and `RATIO_TO_REPORT`.
- Administration pages for sample data maintenance and application theme style selection.

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
| 9 | Use Cases | Entry point for reporting use cases. |
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

The supporting objects create the schema objects and sample data used by the reporting examples.

### Installed Objects

- `EBA_DEMO_IR_PROJECTS`: Main project/task table used by the report, grid, cards, and faceted search examples.
- `EBA_DEMO_IR_PROJECTS_PK`: Unique index on `EBA_DEMO_IR_PROJECTS.ID`.
- `BIU_EBA_DEMO_IR_PROJECTS`: Trigger that generates IDs, maintains `ROW_VERSION_NUMBER`, and validates start/end dates.
- `EBA_DEMO_IR_DEPT`: Department sample table.
- `EBA_DEMO_IR_EMP`: Employee sample table with manager and department relationships.
- `EBA_DEMO_IR_EMP_1`: Index on `EBA_DEMO_IR_EMP.MGR`.
- `EBA_DEMO_IR_EMP_2`: Index on `EBA_DEMO_IR_EMP.DEPTNO`.
- `EBA_DEMO_IR_DATA`: Procedure that reloads project/task and EMP/DEPT sample data.
- `EBA_DEMO_IR_PKG`: Package with pipelined functions used by the page-link reference report.

### Install Scripts

- `set-plscope-settings.sql`: Enables PL/Scope settings for package compilation.
- `create-table.sql`: Creates `EBA_DEMO_IR_PROJECTS`, its primary-key index, and row trigger.
- `emp-and-dept-tables.sql`: Creates the EMP/DEPT sample tables, relationship, and indexes.
- `pipelined-function-package.sql`: Creates `EBA_DEMO_IR_PKG`.
- `load-data.sql`: Creates `EBA_DEMO_IR_DATA` and loads the sample data.

### Upgrade Scripts

- `create-dept-table.sql`: Creates `EBA_DEMO_IR_DEPT` when it is missing.
- `create-emp-table.sql`: Creates `EBA_DEMO_IR_EMP` when it is missing.
- `update-data-script.sql`: Recreates the sample data loading procedure.
- `refresh-data.sql`: Refreshes installed sample data.
- `pipelined-function-package.sql`: Rebuilds `EBA_DEMO_IR_PKG`.
- `drop-old-objects.sql`: Removes obsolete filtering packages and types from older app versions.

### Deinstall

The deinstall script `deinstall-script.sql` removes the demo trigger, tables, procedure, package, and application image files created for the sample application.
