cmake_minimum_required(VERSION 3.2)

# We don't use the C++ compiler, so don't let project()
# test for it in the case the platform doesn't have one
project(MyApp VERSION 4.7.2 LANGUAGES C)

# Primary tool for this project
add_executable(mainTool main.c)

# debugging tool
add_executable(debugger EXCLUDE_FROM_ALL debug.c)

# testing tool
add_executable(tester EXCLUDE_FROM_ALL test.c)

