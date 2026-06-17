# Sample Reporting

This is a custom version of the Original Oracle APEX App which I have modified to:
- Implement as features from the APEX Advisor Scanner as possible
- Adjusted components with the upgrade feature
- Changed the theme to Iris
- Run the APEX Object dependencies for errors
- Add help and accessibility markers

Sample Reporting is an Oracle APEX sample application whose goal is to demonstrate the main reporting patterns available to APEX developers. It provides a working catalog of report pages that show how classic reports, interactive reports, interactive grids, cards, faceted search, SQL examples, analytic SQL, and PL/SQL-based report sources can be used against realistic sample data.

This application requires Oracle APEX 26.1 or a compatible APEX runtime, an Oracle Database schema for the parsing schema and supporting objects, and an import workflow that can install an APEX split export such as SQLcl with APEXlang support or a zipped APEX application import. The database user must be able to create tables, indexes, triggers, procedures, packages, types, and views, because the app installs demo tables, seed data, and PL/SQL objects.

## What Does the App Do?

The app organizes reporting examples into navigable categories so developers can see each reporting feature in context. The home and use-case pages point users toward interactive reports, classic reports, interactive grids, SQL examples, analytic functions, cards, faceted search, and administration pages.

Interactive report pages demonstrate search, filtering, sorting, highlighting, saved report states, pivots, charts, drill-down links, bind-variable filtering, custom button-style report cells, and report links that preserve report state. These pages use the sample project data so the reporting behavior can be explored immediately after installation.

Classic report pages show report filtering, format masks, custom non-tabular templates, collection-backed reports, and source display examples. They are intended to demonstrate how standard SQL queries and APEX page items can be combined to build simple but useful report pages.

Interactive grid pages demonstrate editable grid behavior, drill-down links, report state links, and grid save processing. The cards and faceted search pages reuse the same project data to show alternate ways of browsing, searching, and presenting report-style information.

SQL-focused pages demonstrate common query techniques including `CASE`, inline views, `GROUP BY`, hierarchical `CONNECT BY` queries, `PIVOT`, regular expressions, string functions, `SOUNDEX`, top-N queries, and analytic functions such as `LEAD`, `LAG`, `LISTAGG`, `RANK`, `DENSE_RANK`, `ROW_NUMBER`, and `RATIO_TO_REPORT`. The pipelined functions page shows how PL/SQL package logic can provide tabular data for reporting.

## Page Map

| Page | Name |
| ---: | --- |
| 1 | Interactive Report |
| 2 | Maintain Project |
| 3 | Classic Report |
| 4 | Manage Sample Data |
| 5 | Filtering |
| 6 | Drill Down IR |
| 7 | Highlighting |
| 8 | Format Masks |
| 9 | Use Cases |
| 10 | Home |
| 11 | Interactive Report |
| 12 | Custom Buttons |
| 13 | Non-Tabular Templates |
| 14 | Help |
| 15 | Bind Variables |
| 17 | Interactive Grid |
| 18 | Linking to Interactive Reports |
| 19 | CASE Statement |
| 20 | Top N Queries |
| 21 | Analytic Function Examples |
| 22 | Inline Views |
| 23 | Group By Clause |
| 24 | LEAD and LAG |
| 25 | Pivot Syntax |
| 26 | Connect By |
| 27 | String Functions |
| 28 | Regular Expressions |
| 29 | Soundex |
| 30 | LISTAGG |
| 31 | RANK and DENSE_RANK |
| 32 | ROW_NUMBER |
| 33 | RATIO_TO_REPORT |
| 34 | Application Theme Style |
| 35 | Pipelined Functions |
| 36 | Administration |
| 37 | Linking to Interactive Grids |
| 38 | Report from Collection |
| 39 | SQL Examples |
| 40 | Drill Down IG |
| 41 | Cards |
| 42 | Faceted Search |
| 101 | Login |

## Supporting Objects

The application includes supporting objects that create the schema objects and sample data used by the reporting examples.

### Installed Objects

- `EBA_DEMO_IR_PROJECTS`
- `EBA_DEMO_IR_PROJECTS_PK`
- `BIU_EBA_DEMO_IR_PROJECTS`
- `EBA_DEMO_IR_DEPT`
- `EBA_DEMO_IR_EMP`
- `EBA_DEMO_IR_EMP_1`
- `EBA_DEMO_IR_EMP_2`
- `EBA_DEMO_IR_DATA`
- `EBA_DEMO_IR_PKG`

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

- `deinstall-script.sql`
