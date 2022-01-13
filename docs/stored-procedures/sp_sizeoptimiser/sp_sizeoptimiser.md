---
layout: default
parent: Stored Procedures
has_children: true
nav_order: 4
permalink: /docs/stored-procedures/sp_sizeoptimiser
has_toc: false
---

# sp_sizeoptimiser <!-- omit in toc -->

![sp_sizeoptimiser bag logo]({{ '/assets/images/baggage.png' | relative_url }} "sp_sizeoptimiser bag logo")

- [Purpose](#purpose)
- [Arguments](#arguments)
- [Usage](#usage)
- [Output](#output)

## Purpose

A stored procedure that recommends space saving and corrective data
type measures based on SQL Server database schemas. Great for quickly
assessing databases that may have non-optimal data types. Especially
useful for SQL Server Express to help stay under the 10GB file size limitations.

Storage is cheap, but smaller is faster!

## Arguments

| Parameter | Type | Output | Description |
| --- | --- | --- | --- |
| @IndexNumThreshold | SMALLINT | no | Number of indexes to classify a table as having too many indexes on it. Default value is 10. |
| @IncludeDatabases | SIZEOPTIMISERTABLETYPE | no | Which databases to run the script on in the form of a user defined table type. If not supplied, all accessible user databases are targeted. Cannot be used in conjunction with @ExcludeDatabases. |
| @ExcludeDatabases | SIZEOPTIMISERTABLETYPE | no | Which databases to exclude in the form of a user defined table type. Cannot be used in conjunction with @IncludeDatabases. |
| @IncludeSysDatabases | BIT | no | Whether or not to include system databases in the script's analysis. Default is 0. |
| @IncludeSSRSDatabases | BIT | no | Whether or not to include SQL Server Reporting Services databases in the script's analysis. Default is 0. |
| @Verbose | BIT | no | Whether or not to print additional information during the script run. Default is 0. |
| @IsExpress | BIT | no | Used for unit testing purposes only. |
| @SqlMajorVersion | TINYINT | no | Used for unit testing purposes only. |
| @SqlMinorVersion | SMALLINT | no | Used for unit testing purposes only. |

## Usage

Basic example:

```sql
DECLARE @includeDatabases SizeOptimiserTableType;

INSERT INTO @includeDatabases ([database_name])
VALUES (N'WideWorldImporters');

EXEC [dbo].[sp_sizeoptimiser] @IncludeDatabases = @includeDatabases;
GO
```

## Output

For WorldWideImporters:

[![sp_sizeoptimiser output]({{ '/assets/images/sp_sizeoptimiser_output.png' | relative_url }})]({{ '/assets/images/sp_sizeoptimiser_output.png' | relative_url }})
