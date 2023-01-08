---
layout: default
parent: Stored Procedures
has_children: false
nav_order: 3
--- 

# sp_helpme <!-- omit in toc -->

![sp_helpme medkit logo]({{ '/assets/images/drug.png' | relative_url }} "sp_helpme medkit logo")

- [Purpose](#purpose)
- [Arguments](#arguments)
- [Usage](#usage)
- [Output](#output)

## Purpose

An drop-in modern alternative to sp_help.

Changes from the original include:

- Preferring printed messages over empty result sets for non-applicable data
- Including extended properties wherever possible
- Including create, modify, and more metadata about objects
- Referenced views are returned in two-part naming convention
- Including include columns in index metadata

## Arguments

| Parameter | Type | Output | Description |
| --- | --- | --- | --- |
| @ObjectName | SYSNAME(256) | no | Target object. Default is all objects. |
| @ExtendedPropertyName | SYSNAME(256) | no | Key for extended properties on objects. Default is 'Description'. |
| @SqlMajorVersion | TINYINT | no | Used for unit testing purposes only. |
| @SqlMinorVersion | SMALLINT | no | Used for unit testing purposes only. |

## Usage

Basic example:

```sql
EXEC dbo.sp_helpme 'Sales.Invoices';
```

## Output

For `[Sales].[Invoices]` in WideWorldImporters:

[![sp_helpme output]({{ '/assets/images/sp_helpme_output.png' | relative_url }})]({{ '/assets/images/sp_helpme_output.png' | relative_url }})

[tool]: http://dba-multitool.org
[issue]: https://github.com/LowlyDBA/dba-multitool/issues
