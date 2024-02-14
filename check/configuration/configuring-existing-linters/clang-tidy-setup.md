---
description: How to set up Clang Tidy to work with Trunk Check
---

# Clang Tidy Setup

**Clang-Tidy** is a linter and static analysis tool for checking **C and C++ source code.** It provides additional warnings and checks beyond what the compiler typically provides.  Clang-Tidy comes with many built-in checks and can be extended with an API as well.  Clang-Tidy is part of the [Clang C compiler project ](https://clang.llvm.org/)but can be used with any C/C++ codebase, even if not using Clang.

### Installing Clang-Tidy with Trunk

1. Install [Trunk Check](../../) in your project if you haven’t already.
2. Enable clang-tidy with `trunk check enable clang-tidy`
3. Run `trunk check`

### Configuring  Clang-Tidy with Trunk

If you didn’t previously have clang-tidy enabled, Check will create a `.trunk/configs/.clang-tidy` config file with reasonable defaults for you. You can customize the checks in this file. You can read about specific clang-tidy checks in the main [clang-tidy documentation](https://clang.llvm.org/extra/clang-tidy/).

### Working with CMake

Trunk Check supports [CMake](https://cmake.org/) directly using the `compile_commands.json` file generated by CMake. If you run `cmake` from the `build` directory in the root of your project then Trunk will find the compile commands automatically. If you run it in some other directory then you will have to symlink the `compile_commands.json` in that directory to the root of your repo for Check to find them. _Note that  Check does not currently support CMake out of tree builds._

[More](./#clang-tidy) on working with Clang Tidy and Trunk Check

### Working with Bazel

By default Trunk will query [Bazel](https://bazel.build/) for compile commands used to run clang-tidy, no configuration required. Trunk will build the needed compilation pre-requisites before invoking clang-tidy on each file (e.g. generated protobuf headers). You can generate a local compilation database by running `trunk generate-compile-commands`. Then running `trunk check` will scan your codebase with Clang-Tidy.

[More](./#using-bazel) on working with Bazel & Trunk Check.

### Working with other build systems

Trunk Check currently works only with the CMake and Bazel build systems. If there is another build system you would like Check to work with, please let us know.&#x20;

### See also

Trunk Check also supports [Clang Format](https://docs.trunk.io/check/configuration/configuring-existing-linters#clang-format), a code formatter & beautifier for C/C++ code.&#x20;

[Other linters](https://docs.trunk.io/check/usage/supported-linters) supported by Trunk Check.