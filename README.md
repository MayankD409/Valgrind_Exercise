# Valgrind Exercise

## Standard install via command-line
```bash
# Configure the project and generate a native build system:
  # Must re-run this command whenever any CMakeLists.txt file has been changed.
  cmake -S ./ -B build/
# Compile and build the project:
  # rebuild only files that are modified since the last build
  cmake --build build/
  # or rebuild everything from scracth
  cmake --build build/ --clean-first
  # to see verbose output, do:
  cmake --build build/ --verbose
# Run program:
  ./build/app/shell-app
# Clean
  cmake --build build/ --target clean
# Clean and start over:
  rm -rf build/
```
## What happens when the executable is linked statically?  

When an executable is linked statically, it means that all the necessary libraries and dependencies are included within the executable file itself. This results in a larger executable file that doesn't rely on external shared libraries during runtime. Statically linking can enhance portability and reduce dependencies on specific library versions installed on the target system.
## Does Valgrind still detect those same bugs? Why?

Valgrind can still be used to detect certain types of bugs, such as memory leaks and invalid memory accesses, because it operates at the level of machine instructions and memory accesses. However, there are limitations when it comes to detecting issues related to dynamically loaded libraries and functions. If a program uses dynamic libraries and Valgrind is not able to track those libraries (which is the case with statically linked executables), it won't be able to analyze issues specific to those libraries.




