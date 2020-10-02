# Valgrind
---

## Overview

Valgrind is a tool to improve code quality during development and testing. Valgrind helps detect several types of code issues:

* Undefined behavior
* Function and memory profiling
* Data-race detection
* Memory leak detection


## Standard install via command-line
```
git clone --recursive https://github.com/SantoshKesani/Valgrind.git
cd <path to repository>
mkdir build
cd build
cmake ..
make
Run tests: ./test/cpp-test
Run program: ./app/shell-app
```

## Building for code coverage
```
sudo apt-get install lcov
cmake -D COVERAGE=ON -D CMAKE_BUILD_TYPE=Debug ../
make
make code_coverage
```
This generates a index.html page in the build/coverage sub-directory that can be viewed locally in a web browser.

## Valgrind Outputs

The following commands were run in the directory and the detected two bugs were fixed

* valgrind ./app/shell-app
* valgrind --tool=helgrind ./app/shell-app
* valgrind --leak-check=full ./app/shell-app

The valgrind outputs before and after fixing the bugs are added to the repository as Before_fixing_bugs and After_fixing_bugs.
KCachegrind output is also attached to the repository as Kcachegrind.
