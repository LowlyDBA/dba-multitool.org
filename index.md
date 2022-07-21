---
layout: default
title: DBA MultiTool
nav_order: 1
description: "T-SQL scripts for the long haul: optimizing storage, on-the-fly documentation, and general administrative needs."
permalink: /
---

# DBA MultiTool
{: .fs-9 }

 T-SQL scripts for the long haul: optimizing storage, on-the-fly documentation, and general administrative needs.
{: .fs-6 .fw-300 }

[Get started now](#getting-started){: .btn .btn-primary .fs-5 .mb-4 .mb-md-0 .mr-2 } [View it on GitHub](https://dba-multitool.org/github){: .btn .fs-5 .mb-4 .mb-md-0 }

---

## Getting started

### T-SQL installation

1. Download the latest [version](https://github.com/LowlyDBA/dba-multitool/archive/refs/heads/master.zip).

2. Run `install_dba-multitool.sql` to install all scripts:

    ```bat
    sqlcmd -S localhost -d master -i install_dba-multitool.sql
    ```

3. Check the [documentation]({{ '/docs/stored-procedures' | relative_url }}) for parameter use for each stored procedure.

### PowerShell installation: use DBATools

1. If needed, install [DBATools](https://dbatools.io/):

    ```powershell
    Install-Module DBATools
    ```

2. Install DBA MultiTool:

    ```powershell
    Install-DbaMultiTool -SqlInstance server1 -Database master
    ```

3. Check the [documentation]({{ '/docs/stored-procedures' | relative_url }}) for parameter use for each stored procedure.

## About the project

DBA MultiTool is &copy; 2017-{{ "now" | date: "%Y" }} by [John McCall aka LowlyDBA](https://lowlydba.com).

### License

DBA MultiTool is distributed by an [MIT license](https://dba-multitool.org/license).

### Contributing

Read about becoming a contributor in [our GitHub repo](https://dba-multitool.org/contributing).

### Code of Conduct

DBA MultiTool is committed to fostering a welcoming community.

[View our Code of Conduct](https://dba-multitool.org/code-of-conduct) on our GitHub repository.
