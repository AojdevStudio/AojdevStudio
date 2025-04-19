<!-- === WATCHER HEADER START === -->
<!-- File: myrules/codebased-rules/python/watchful-headers.md -->
<!-- Managed by file watcher -->
<!-- === WATCHER HEADER END === -->
### How This Helps LLMs

Long conversations or complex projects can cause the context of file paths and project structure to become obscured. By including explicit header information that shows each file's location within the overall project tree, both developers and LLM-based coding assistants are provided with clear context. This mitigates common issues such as:

- Duplicating files by forgetting existing entries
- Losing track of how individual files relate to the larger codebase
- Overlooking important structural context during long modification sessions

This way, when an LLM is assisting with code modifications, it can reference the file's placement and relationships, ensuring consistent and context-aware modifications even when conversation history becomes very lengthy.

## Features

- Automatically adds and updates headers in watched files
- Maintains a live project tree structure in `.cursorrules`
- Supports multiple file types with appropriate comment syntax
- Dynamic watching of new files and directories
- Debounced file updates to prevent excessive writes
- Thread-safe header management



## Using in Your Project

### Option 1: Installing via Script (Recommended)

If you want to add the watcher to an existing project:

1. From your project root, clone and install:
   ```bash
   git clone https://github.com/johnbenac/cursor-watchful-headers.git
   python cursor-watchful-headers/install.py
   ```

2. The script will:
   - Copy `watcher.py` and `.watchlist` to your current directory (if they don't already exist)
   - Install the required `watchdog` package
   - Leave your existing `requirements.txt` untouched
   - Leave your existing `.cursorrules` untouched (at least until you run watcher.py)

3. You can now delete the cloned directory if desired (the copied files in your current directory will remain):
   ```bash
   rm -rf cursor-watchful-headers  # On Windows: rmdir /s /q cursor-watchful-headers
   ```
