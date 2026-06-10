#Salesforce LogExplorer: Cloud Log Retrieval & Debugging Assistant 🚀

Salesforce LogExplorer is an IntelliJ IDEA plugin that uses the Salesforce CLI to download Apex debug logs directly into your project, organized by user and date, so you can search, browse and debug them without ever leaving the IDE.

🛠️ Found a bug or have a suggestion? Open an issue on GitHub — your feedback helps improve the plugin!

##✨ Features:
📂 Download Apex logs via Salesforce CLI and save them locally, organized by user and date. Only new logs are downloaded on subsequent runs.
👤 Filter log retrieval by username — only download logs from the users you care about.
🔄 LogTail: automatically poll for new logs at a configurable interval — start and stop with one click, no manual refresh needed.
🗂️ Log Explorer Panel: browse all downloaded logs in a dedicated tool window, filterable by user, date, time and size. Full-text search across log files with inline preview, highlight navigation and one-click IC Debugger integration.
🔍 View log details (user, size, status, duration) directly in the editor banner when opening a log file.
⚙️ One-click IlluminatedCloud integration (thanks to Scott Wells): open any log directly in the IC debugger from the editor banner — no manual copying required.

##⚙️ Requirements:
Salesforce CLI must be installed and accessible. Configure the path in the plugin settings if needed.
IlluminatedCloud 2 is optional but required for the one-click debugger integration.
💡 Salesforce LogExplorer is ideal for developers looking for a faster way to retrieve and debug Salesforce logs without leaving their IDE.


## 📝 Changelog
### • 1.4.2
- ➕ Log preview now highlights USER_DEBUG lines in green so they stand out at a glance
- ➕ New "Debug only" toggle in the filter bar shows just the USER_DEBUG lines in the preview
- ✔ Fixed NullPointerException and unusable green/blank preview occurring after repeatedly pressing "Open in IC Debugger"

### • 1.4.1
- ✔ Fixed crash on "Open in IC De si sbianbugger" button in IntelliJ 2026.1 (read access threading violation)
- 📊 Log preview now uses a native IntelliJ editor (soft-wrap, IDE font/theme, Ctrl+F search)
- 🔧 Build target updated to IntelliJ 2026.1
- ➕ Exclusion rules: right-click a log to hide all logs matching by ID, operation, application or status — rules are persisted per project, togglable without deletion, and managed via a sidebar icon button

### • 1.4.0
- ➕ New Log Explorer Panel: ToolWindow (bottom-right) and Dialog showing all downloaded logs in a table, filterable by user, date, time and minimum size
- ➕ Full-text search across log files with inline preview and highlight navigation (global + preview, combined mode)
- ➕ Log metadata (Id, Operation, Application, Status, Duration) saved locally to metadata.json after each download — no Salesforce query needed to browse logs
- 📊 Editor banner now reads metadata.json instantly instead of querying Salesforce CLI on every open
- ✔ Fixed editor banner cache race condition — repeated opens of the same log no longer re-query Salesforce
- ✔ Fixed log limit setting: value 10 was incorrectly reset to the maximum on restart
- ✔ Fixed regression in log download: SOQL query was filtering by Id instead of LastModifiedDate, causing incorrect or missing results

### • 1.3.0
- ✔ Fixed Tail starting multiple concurrent download batches without waiting for the previous one to complete
- ✔ Fixed download getting stuck at the end due to process stdout buffer deadlock
- ✔ Fixed orphaned log files left in temp folder after an interrupted download now being correctly moved to their destination
- ✔ Fixed Stop Tail cancelling timers of all open projects instead of only the current one
- ✔ Fixed timer leak in progress indicator listener not being cancelled on normal process completion
- ✔ Fixed potential SOQL injection in username and log ID queries
- 📊 Improved download performance: replaced CPU-intensive busy-wait loop with thread join

### • 1.2.0
- ✔ Added compatibility with 2025.3.*
- ✔ Other fixes and improvements

### • 1.0.15
- ➕ Extended compatibility to 2025.*
- ➕ Do to some breaking changes to the JB plugin API the minimum supported version has been bumped to 2024.3.5
- ✔ Other fixes and improvements

### • 1.0.14
- ✅ Fixed bug occurring when removing usernames from the settings  
- ✅ Fixed setting page not being displayed on IJ < 2024

### • 1.0.13
- ✅ Improved log querying now using SOQL instead of CLI command  
- ➕ Added possibility to download only logs from users specified in the settings

### • 1.0.12
- ✅ Fixed a bug where settings were not displaying correctly  
- ➕ LogTail Notification can now be silenced!

### • 1.0.11
- ➕ New functionality: LogTail!  
- ⚠️ Notification may be annoying while using the new Tail functionality

### • 1.0.10
- ➕ Now LogExplorer settings are per project  
- ✅ Fixed a bug where logs were downloading more than once  
- ✅ Removed static variables as they were causing issues when multiple IJ instances were open

### • 1.0.9
- ✅ Hopefully a fix for the previous issue  
- ➕ Added new setting: "Is the project in a subfolder?" Set this to true only if the actual project files are in a subfolder

### • 1.0.8
- 🔧 Added workaround for cases where the main project is in a subfolder

### • 1.0.7
- ⚙️ Project refactoring  
- ➕ Introduced new setting: "Get target-org from project file"

### • 1.0.6
- 🐛 Fixed indexing issue (logs couldn't be searched via CTRL+SHIFT+F) after additional retrieval

### • 1.0.5
- 📊 Optimized project view refresh  
- 📊 Extension now works with multiple instances of IJ open  
- 💾 Cached "Get target-org" API call

### • 1.0.4
- 🔧 Added configuration under settings

### • 1.0.3
- 🔧 Preparing for a complete redo  
- 💾 Downloaded logs are now cached  
- 🏗️ Improved performance overall  
- ⚙️ Various fixes and enhancements

### • 1.0.2
- 📥 Added bulk log download

### • 1.0.0
- 🚀 Initial release
