# 🚀 C++ PRO BUILDER (NO-CMAKE)

This VS Code Extension provides a professional, zero-setup environment for compiling C and C++ single files on Windows (PowerShell) without the need for complex CMake configuration.

It solves the common problem of messy root directories by automatically organizing all compiled executables (`.exe` files) into a dedicated `build` folder.

## ✨ Features

* **Automatic Setup:** Automatically installs the required `Code Runner` extension upon installation.
* **Clean Architecture:** Organizes compiled files into language-specific folders:
    * C++ executables go to: `workspace/build/cpp/source_folder/file.exe`
    * C executables go to: `workspace/build/c/source_folder/file.exe`
* **Conflict-Free:** Prevents naming conflicts between `test.c` and `test.cpp` files in the same directory.
* **Space Handling:** Correctly handles file names containing spaces (e.g., `salam copy.cpp`).
* **PowerShell Logic:** Uses robust PowerShell scripting to ensure reliable cross-folder compilation.

## 💡 How to Use

1.  **Install the Extension:** Search for "C++ Pro Builder" (or your extension's final name) in the VS Code Marketplace, or install the `.vsix` file.
2.  **Open a Folder:** Open the main folder of your C/C++ project in VS Code.
3.  **Run:** Open any `.cpp` or `.c` file inside your project.
4.  Press the **Run Button** (the green triangle) or use the shortcut **`Ctrl+Alt+N`**.

The executable will be generated in the correct `build` subdirectory, and the output will appear in the Integrated Terminal.

## ⚙️ Configuration (Contributed Settings)

This extension automatically sets the following configurations:

| Setting | Value | Description |
| :--- | :--- | :--- |
| `code-runner.runInTerminal` | `true` | Ensures input/output works correctly. |
| `code-runner.saveFileBeforeRun` | `true` | Prevents compiling unsaved changes. |
| `code-runner.executorMap` | Custom PowerShell Script | Contains the custom logic for path manipulation and compilation (`gcc`/`g++`). |

---