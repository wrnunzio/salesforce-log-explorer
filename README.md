# 🚀 Salesforce LogExplorer: Cloud Log Retrieval & Debugging Assistant

**Salesforce LogExplorer** is an IntelliJ IDEA plugin in **beta**, designed to simplify your debugging process when working with Salesforce logs. While still evolving, it provides tools to streamline log retrieval, exploration, and debugging.

## ✨ Features:

- 📂 Retrieve and save Salesforce logs directly in your IDE.
- 👤 Select which logs to retrieve by specifying the user in the plugin settings.
- 🔍 View log details, such as size, status, and user information, within your editor.
- ⚙️ Integrated with **IlluminatedCloud** (thanks to Scott Wells) to open logs directly in the debugger—no manual copying required.
- 🛠️ A helpful message at the top of each opened log displays key details and includes a one-click option to debug instantly.

💡 **Salesforce LogExplorer** is ideal for developers looking for an easier way to manage Salesforce logs. Try it out and see how it can save you time as it continues to grow and improve!


## 📝 Changelog

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
