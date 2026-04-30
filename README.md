# getDll

**getDll** is a minimal C++ library that simplifies working with the Windows API by providing a single function to retrieve all loaded DLLs of a target process.

---

## 🚀 Features

* Simple and beginner-friendly
* Wraps complex WinAPI calls
* Returns all loaded modules (DLLs) as a `std::vector<std::string>`
* No unnecessary overhead – just one function

---

## 📦 Usage

```cpp
#include "process_test.h"

int pid = 1234; // target process ID
std::vector<std::string> dlls = grabDlls(pid);

for (const auto& dll : dlls)
{
    std::cout << dll << std::endl;
}
```

---

## 🧠 What it does

Internally, `getDll` uses Windows API functions like:

* `OpenProcess`
* `EnumProcessModules`
* `GetModuleFileNameEx`

This allows you to enumerate all modules loaded in a process without dealing with low-level WinAPI complexity.

---

## 🔧 Requirements

* Windows OS
* C++17 or higher
* Linking against:

  * `Psapi.lib`

---

## 📁 Project Structure

```
getDll/
├── process_test.h
├── process_test.cpp
└── getDll.lib
```

---

## 🎯 Goal

This library is designed for beginners who want to explore Windows internals without getting overwhelmed by raw WinAPI usage.
It abstracts the complexity into a single, easy-to-use function.

---

## ⚠️ Notes

* Requires appropriate permissions to open target processes
* May fail on protected/system processes

---

## 📌 Example Use Cases

* Learning Windows internals
* Building debuggers or analyzers
* Malware analysis (basic)
* Process inspection tools

---

## 🛠 Future Ideas

* Get base addresses of modules
* Filter specific DLLs
* Convert to header-only version
* Add process listing utilities

---

## 📄 License

MIT (or whatever you choose)
