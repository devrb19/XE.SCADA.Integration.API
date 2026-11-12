# XE.SCADA.Integration.API



------------------------------------------------------Files------------------------------------------------------

File / Folder					Purpose

Controllers			Where we'll keep our API controllers
Properties			Project launch and debugging settings
Dependencies			Installed packages and project references
Program.cs			Application startup and service configuration
appsettings.json		Application configuration
appsettings.Development.json	Development-specific settings


------------------------------------------------------Tables------------------------------------------------------

Table Name XEAPI

01_XE_Heat_Treatment_GET_Tables.sql
- ADM_TBL_Heat_Treatment_Furnace
- QA_TBL_Heat_Treatment_Header
- QA_TBL_Heat_Treatment_Temperature

02_XE_SCADA_Integration_POST_Tables.sql
- QA_TBL_HT_SCADA_Process_Data
- QA_TBL_HT_SCADA_Process_Parameter
- QA_TBL_HT_SCADA_Alarm
- INT_TBL_SCADA_Integration_Log

------------------------------------------------------Packages Installed------------------------------------------------------

NuGet Manager
Microsoft.EntityFrameworkCore.SqlServer  > Stable 10.0.15
- Microsoft.EntityFrameworkCore.Design     > Stable 10.0.15
- Microsoft.EntityFrameworkCore.Tools      > Stable 10.0.15

Generate C# classes from your seven database tables

Tools → NuGet Package Manager → Package Manager Console.
In the Package Manager Console, set Default project to XE.SCADA.Integration.API



------------------------------------------------------API's------------------------------------------------------

API 1: Get List of Unsynced Heat Treatment Batches.

According to Section 6.1, its proposed endpoint is:

GET /api/heat-treatment/batch/unsynced
Property		Purpose indicated by its name
ScadaSyncStatusId	SCADA synchronization status
ScadaSyncedDate		Date/time of synchronization
ScadaSyncCount		Number of synchronization attempts or occurrences
