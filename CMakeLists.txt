cmake_minimum_required(VERSION 3.14)
project(scratch)

set(CMAKE_CXX_STANDARD 14)
set(CMAKE_CXX_STANDARD_REQUIRED ON)

# Set compiler flags (including -g for debugging information)
set(CMAKE_CXX_FLAGS "${CMAKE_CXX_FLAGS} -g")

#
# Create the compilation database for clangd and move it out of the build dir.
#
set(CMAKE_EXPORT_COMPILE_COMMANDS ON) # Enable compile_commands.json
execute_process(COMMAND cmake -E create_symlink
                "${PROJECT_BINARY_DIR}/compile_commands.json"
                "${PROJECT_SOURCE_DIR}/compile_commands.json")


# Just a simple app               
add_subdirectory(app)

