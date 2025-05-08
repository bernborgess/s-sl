cmake_minimum_required(VERSION 3.11)

set(CMAKE_C_STANDARD 99)
set(CMAKE_C_STANDARD_REQUIRED ON)
set(CMAKE_RUNTIME_OUTPUT_DIRECTORY ${CMAKE_BINARY_DIR}/bin)

project (ssl VERSION 1.0.0 LANGUAGES C)

# Add sources
file(GLOB_RECURSE SOURCES ${CMAKE_SOURCE_DIR}/src/*.c)
file(GLOB_RECURSE HEADERS ${CMAKE_SOURCE_DIR}/src/*.h)

# Create lib
add_executable(${PROJECT_NAME} ${SOURCES} ${HEADERS})

# Add compile options
target_compile_options(${PROJECT_NAME} PRIVATE -O3 -Wall -Wextra -pedantic -Wno-unused-parameter -Wno-sign-compare)
