# Qore Compilation and Execution Instructions

This document provides step-by-step instructions for compiling the Qore program using G++ with V8 integration, and then running the compiled executable.

## Compilation

To compile the Qore program, use the following command:

```bash
g++ -std=c++20 -DV8_COMPRESS_POINTERS -DV8_ENABLE_SANDBOX -DV8_TARGET_ARCH_ARM64 -I/opt/homebrew/include -I/opt/homebrew/Cellar/v8/12.7.224.16/include qore.cpp -o qore -L/opt/homebrew/lib -lv8 -lv8_libplatform -lv8_libbase
```

### Command Breakdown:

- `g++`: The C++ compiler
- `-std=c++20`: Use C++20 standard
- `-DV8_COMPRESS_POINTERS -DV8_ENABLE_SANDBOX -DV8_TARGET_ARCH_ARM64`: V8-specific compiler flags
- `-I/opt/homebrew/include -I/opt/homebrew/Cellar/v8/12.7.224.16/include`: Include directories for V8 headers
- `qore.cpp`: The main source file
- `-o qore`: Output executable name
- `-L/opt/homebrew/lib`: Library search path
- `-lv8 -lv8_libplatform -lv8_libbase`: Link against V8 libraries

## Execution

After successful compilation, run the Qore executable with the following command:

```bash
./qore
```

This command assumes you're in the same directory as the compiled `qore` executable. If you're in a different directory, provide the full path to the executable.

## Notes

- Ensure that V8 is properly installed on your system, preferably using Homebrew as indicated by the include paths.
- The V8 version used in this compilation is 12.7.224.16. If you have a different version, adjust the include path accordingly.
- Make sure `qore.cpp` and `Qore.js` are in the same directory when running the executable, as the C++ program likely loads the JavaScript file.

If you encounter any issues during compilation or execution, check your V8 installation and ensure all paths are correct for your system setup.
