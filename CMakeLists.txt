cmake_minimum_required(VERSION 3.20)
project(COFFLoader LANGUAGES C CXX)

set(CMAKE_CXX_STANDARD 17)

# COFFLoader executable
add_executable(COFFLoader
    Src/main.cpp
    Src/coff_loader.cpp
    Src/utils.cpp
    Src/beacon_compatibility.c
)
target_include_directories(COFFLoader PRIVATE Include)
target_link_libraries(COFFLoader PRIVATE advapi32)

# Build BOFs from submodule
add_subdirectory(Beacon-Object-File-Library)
