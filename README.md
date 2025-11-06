# Linux File Explorer Application

A comprehensive console-based file explorer application written in C++ for Linux operating systems. This application provides a complete file management system with navigation, manipulation, search, and permission management capabilities.

## 📋 Project Overview

**Assignment:** Capstone Project - File Explorer Application  
**Language:** C++  
**Platform:** Linux OS  
**Development Time:** 5 Days

## 🎯 Features

### Day 1: Basic Operations
- ✅ List files in current directory (simple and detailed views)
- ✅ Display file information with color coding
- ✅ Show file sizes, modification times, and types

### Day 2: Navigation
- ✅ Change directories (absolute and relative paths)
- ✅ Navigate to parent directory
- ✅ Display current working directory
- ✅ Real-time directory tracking

### Day 3: File Manipulation
- ✅ Create new files
- ✅ Create new directories
- ✅ Delete files and directories
- ✅ Copy files
- ✅ Move/Rename files

### Day 4: Search Functionality
- ✅ Recursive file search
- ✅ Case-insensitive filename matching
- ✅ Search in current directory or entire system
- ✅ Display search results with full paths

### Day 5: Permission Management
- ✅ View file permissions (symbolic and octal)
- ✅ Change file permissions (chmod)
- ✅ Change file ownership (chown)
- ✅ Display owner and group information
- ✅ Show detailed file statistics

## 🛠️ Prerequisites

- Linux operating system (Ubuntu, Debian, Fedora, etc.)
- G++ compiler (version 4.8 or higher)
- Make utility
- Standard C++ libraries
- Root/sudo access (optional, for some permission operations)

## 📦 Installation

### 1. Clone or Download the Project

```bash
cd /path/to/project
```

### 2. Compile the Application

**Using Make:**
```bash
make
```

**Manual Compilation:**
```bash
g++ -Wall -Wextra -std=c++11 -O2 -o file_explorer file_explorer.cpp
```

### 3. Run the Application

```bash
./file_explorer
```

### 4. Optional: System-wide Installation

```bash
make install
```

This installs the application to `/usr/local/bin/` so you can run it from anywhere:
```bash
file_explorer
```

## 🎮 Usage Guide

### Main Menu Options

```
Navigation & Listing:
  1.  List files (simple)           - Basic file listing
  2.  List files (detailed)         - Detailed view with permissions, size, etc.
  3.  Change directory              - Navigate to a specific directory
  4.  Go to parent directory        - Move up one directory level

File Operations:
  5.  Create file                   - Create a new empty file
  6.  Create directory              - Create a new directory
  7.  Delete file/directory         - Remove a file or empty directory
  8.  Copy file                     - Copy a file to another location
  9.  Move/Rename file              - Move or rename a file

Search:
  10. Search files                  - Recursively search for files by name

Permissions Management:
  11. View file permissions         - Display detailed permission information
  12. Change permissions (chmod)    - Modify file permissions
  13. Change owner/group (chown)    - Change file owner/group

Other:
  14. Display current path          - Show the current working directory
  0.  Exit                          - Exit the application
```

### Example Usage Scenarios

#### 1. Navigate and List Files
```bash
Choice: 3
Enter directory path: /home/user/Documents
Choice: 2 (for detailed listing)
```

#### 2. Create and Manage Files
```bash
Choice: 5
Enter filename: test.txt

Choice: 6
Enter directory name: my_folder
```

#### 3. Search for Files
```bash
Choice: 10
Enter search term: config
# Searches recursively for all files containing "config" in their name
```

#### 4. Change Permissions
```bash
Choice: 12
Enter filename: script.sh
Enter permissions (octal): 755
# Makes the file executable (rwxr-xr-x)
```

#### 5. View File Details
```bash
Choice: 11
Enter filename: document.txt
# Shows permissions, owner, group, size, and modification time
```

## 🎨 Color Coding

The application uses color coding for better visual organization:

- **Blue (Bold)** - Directories
- **Green** - Executable files
- **White** - Regular files
- **Red** - Error messages
- **Green** - Success messages
- **Yellow** - Warnings and menu headers
- **Cyan** - Information and current path

## 📝 Technical Details

### System Calls Used
- `opendir()`, `readdir()`, `closedir()` - Directory operations
- `stat()` - File information retrieval
- `mkdir()` - Directory creation
- `rmdir()`, `unlink()` - Deletion operations
- `rename()` - Move/rename operations
- `chmod()` - Permission modification
- `chown()` - Ownership modification
- `getcwd()`, `chdir()` - Directory navigation

### File Permission Format
Permissions are displayed in both symbolic and octal formats:
- **Symbolic:** `drwxr-xr-x` (d=directory, r=read, w=write, x=execute)
- **Octal:** `755` (7=rwx, 5=r-x, 5=r-x)

### Permission Breakdown
```
Owner  Group  Others
rwx    r-x    r-x
421    421    421
 7      5      5
```

## 🔐 Permissions Required

### Standard Operations
- Reading, listing, searching: User read permissions
- Creating, copying files: User write permissions
- Executing, navigating: User execute permissions

### Administrative Operations (require sudo)
- Changing ownership with `chown`
- Modifying permissions on system files
- Accessing restricted directories

## 🐛 Error Handling

The application includes comprehensive error handling for:
- Invalid directory paths
- Permission denied errors
- File not found errors
- Invalid input validation
- Directory deletion of non-empty directories

## 🚀 Advanced Features

### Recursive Search
The search function recursively traverses all subdirectories to find matching files.

### Smart File Sizing
File sizes are automatically formatted with appropriate units (B, KB, MB, GB, TB).

### Safety Confirmations
Destructive operations (like deletion) require user confirmation to prevent accidental data loss.

### Cross-Platform Path Handling
Supports both absolute (`/home/user/file`) and relative (`../folder/file`) paths.

## 📊 Project Structure

```
File Explorer/
├── file_explorer.cpp    # Main application source code
├── Makefile            # Build configuration
└── README.md           # This file
```

## 🔧 Compilation Options

### Debug Build
```bash
g++ -Wall -Wextra -std=c++11 -g -o file_explorer_debug file_explorer.cpp
```

### Optimized Release Build
```bash
g++ -Wall -Wextra -std=c++11 -O3 -o file_explorer file_explorer.cpp
```

## 📚 Learning Outcomes

This project demonstrates:
1. **Linux System Programming** - Direct interaction with OS through system calls
2. **File System Operations** - Understanding of file system structure and operations
3. **Process Management** - Working with permissions, ownership, and file attributes
4. **C++ Programming** - Object-oriented design, STL usage, and modern C++ features
5. **User Interface Design** - Creating intuitive console-based interfaces
6. **Error Handling** - Robust error checking and user feedback

## 🤝 Day-wise Implementation Guide

### Day 1: Foundation (✅ Complete)
- Application architecture design
- Basic file listing functionality
- Color-coded output system

### Day 2: Navigation (✅ Complete)
- Directory navigation implementation
- Path handling (absolute/relative)
- Current directory tracking

### Day 3: Manipulation (✅ Complete)
- File creation and deletion
- Directory operations
- Copy and move functionality

### Day 4: Search (✅ Complete)
- Recursive search algorithm
- Pattern matching implementation
- Result display formatting

### Day 5: Permissions (✅ Complete)
- Permission viewing system
- chmod implementation
- chown implementation
- User/group information display

## ⚠️ Important Notes

1. **Root Privileges:** Some operations (like changing ownership or accessing system directories) may require root privileges. Run with `sudo` when necessary.
2. **Empty Directories Only:** The delete operation only works on empty directories. To delete non-empty directories, implement recursive deletion (use with caution).
3. **File Overwriting:** Copy operations will overwrite existing files without warning. Add checks if needed.
4. **Symbolic Links:** The application handles symbolic links but displays them as regular files in simple mode.

## 🔄 Future Enhancements

Potential improvements:
- Recursive directory deletion
- File preview/viewing
- Archive operations (zip/tar)
- File filtering and sorting options
- Bookmark favorite directories
- Command history
- Batch operations
- File comparison tool

## 📄 License

This is an educational project developed as part of a capstone assignment.

## 👨‍💻 Development Information

**Development Period:** 5 Days  
**Testing Platform:** Linux (Ubuntu/Debian compatible)  
**Compiler:** G++ with C++11 standard  

---

## 🎓 Conclusion

This File Explorer application successfully implements all required features across the 5-day development timeline, providing a comprehensive file management solution for Linux systems with an intuitive console-based interface.

**Happy Exploring! 🚀**