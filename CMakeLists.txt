cmake_minimum_required(VERSION 3.0.0)
project(hello-world VERSION 0.1.0 LANGUAGES C CXX)

include(CTest)
enable_testing()

add_executable(hello-world src/main.cpp)

set(CPACK_PROJECT_NAME ${PROJECT_NAME})
set(CPACK_PROJECT_VERSION ${PROJECT_VERSION})
include(CPack)

cmake_minimum_required(VERSION 3.12)
project(YourProjectName)

# Find lldb
find_program(LLDB_EXECUTABLE NAMES lldb)

# Set the debugger to lldb if found
if(LLDB_EXECUTABLE)
    set(CMAKE_CXX_DEBUGGER "${LLDB_EXECUTABLE}")
    set(CMAKE_CXX_FLAGS_DEBUG "${CMAKE_CXX_FLAGS_DEBUG} -g")
else()
    message(FATAL_ERROR "lldb not found. Make sure it is installed.")
endif()

# Add your project's source files and other configurations here...
