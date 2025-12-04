# 🚀 C++ PRO BUILDER (NO-CMAKE)

[![VS Code Marketplace Version](https://img.shields.io/visual-studio-marketplace/v/YourPublisher.cpp-pro-builder?color=blue&label=Marketplace)](https://marketplace.visualstudio.com/items?itemName=YourPublisher.cpp-pro-builder)
[![GitHub license](https://img.shields.io/github/license/Camalzadeh/cpp-pro-builder)](LICENSE)

This **VS Code Extension** provides a professional, zero-setup environment for compiling C and C++ single files on **Windows (PowerShell)** without the overhead of **CMake** or complex build systems.

It solves the two most common development frustrations: **messy root directories** and **build conflicts**.

---

## ✨ Key Features

* **Clean Architecture:** Organizes all compiled executables (`.exe` files) into a dedicated `build` folder, mirroring the source structure (e.g., `src/main.cpp` -> `build/cpp/src/main.exe`).
    * C++ executables go to: `workspace/build/cpp/source_folder/file.exe`
    * C executables go to: `workspace/build/c/source_folder/file.exe`
* **🌳 Build Structure Visualization**
    When compiling a file located deep within your source directory (e.g., `src/data_processing/parser.cpp`), the extension ensures the build output maintains the same relative path structure inside the dedicated `build` folder.

    This prevents executables from cluttering your source code directories.

    ```
    your-project-root/
    ├── .vscode/               (VS Code settings)
    ├── src/
    │   ├── main.cpp
    │   └── data_processing/
    │       └── parser.cpp
    ├── build/                 <-- ALL EXECUTABLES ARE HERE
    │   ├── cpp/               <-- C++ binaries
    │   │   ├── main.exe       <-- main.cpp executable
    │   │   └── data_processing/
    │   │       └── parser.exe <-- parser.cpp executable
    │   └── c/                 <-- C binaries (if applicable)
    │       └── driver.exe
    └── README.md
    ```
* **Zero Conflict Guarantee:** Prevents naming conflicts between `test.c` and `test.cpp` files in the same directory.
* **Space Handling:** Correctly handles complex file names containing spaces (e.g., `main test.cpp`).
* **PowerShell Logic:** Uses robust PowerShell scripting to ensure reliable cross-folder compilation.
---

## 💡 Quick Start

1.  **Installation:** Install the **C++ Pro Builder** extension from the VS Code Marketplace.
2.  **Open Folder:** Open the main folder of your C/C++ project in VS Code (**File > Open Folder**).
3.  **Run:** Open any `.cpp` or `.c` file and press the **Run Button** (the green triangle) or use the shortcut **`Ctrl+Alt+N`**.

The executable will be generated in the correct `build` subdirectory, and the output will appear directly in the **Integrated Terminal**.

---
## 📦 Installation Options

There are two primary ways to install the extension:

### 1. VS Code Marketplace (Future Release) 🌟

* Once the extension is published, simply search for **"C++ Pro Builder (No-CMake)"** in the VS Code Extensions view and click 'Install'.

### 2. Manual VSIX Installation (Current Method) 🛠️

Since the extension is not yet in the Marketplace, you must get the `.vsix` file directly from GitHub:

1.  Go to the **[GitHub Repository Releases Page](https://github.com/Camalzadeh/cpp-pro-builder/releases)**.
2.  Download the latest `cpp-pro-builder-X.X.X.vsix` file.
3.  Open **VS Code**.
4.  Navigate to the **Extensions** view (Ctrl+Shift+X).
5.  Click the **More Actions (...)** menu (three dots) and select **Install from VSIX...**
6.  Select the downloaded `.vsix` file to install the custom build configuration.

---

## ⚙️ Configuration Details

This extension works by contributing specific configurations to your user settings, ensuring a seamless experience.

| Setting | Value | Description |
| :--- | :--- | :--- |
| `code-runner.runInTerminal` | `true` | **Crucial:** Ensures I/O operations (`std::cin`/`std::cout`) function correctly by running the executable in the Integrated Terminal (PowerShell). |
| `code-runner.saveFileBeforeRun` | `true` | Prevents compiling unsaved code. |
| `code-runner.executorMap` | Custom PowerShell Script | Contains the advanced logic for path cleaning (`.Trim()`, `.Replace()`), dynamic folder creation (`mkdir`), and execution via `g++` or `gcc`. |

### 🧑‍💻 Manual Installation (for VSIX)

If you downloaded the `.vsix` file directly:
1.  Open VS Code.
2.  Go to the Extensions view (Ctrl+Shift+X).
3.  Click the `...` menu (More Actions) -> **Install from VSIX...**
4.  Select the `cpp-pro-builder-1.0.0.vsix` file.

---

## 🤝 Contribution

This project is open source and based on the standard `g++` and `gcc` compilers found in MinGW/WSL/etc. If you find a bug or have a suggestion, please open an issue or submit a pull request on the [GitHub repository](https://github.com/Camalzadeh/cpp-pro-builder).

**Keywords:** `C++`, `C`, `Builder`, `Code Runner`, `No-CMake`, `PowerShell`, `Single File`