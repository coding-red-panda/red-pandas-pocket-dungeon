cmake_minimum_required(VERSION 3.28)
project(red-pandas-pocket-dungeon LANGUAGES CXX)

set(CMAKE_RUNTIME_OUTPUT_DIRECTORY build/bin)

include(FetchContent)

# ---- SFML static build options ----
set(SFML_BUILD_SHARED_LIBS OFF CACHE BOOL "" FORCE)
set(SFML_STATIC_LIBRARIES ON CACHE BOOL "" FORCE)

# Optional: disable what you don't need
set(SFML_BUILD_NETWORK OFF CACHE BOOL "" FORCE)

FetchContent_Declare(SFML
    GIT_REPOSITORY https://github.com/SFML/SFML.git
    GIT_TAG 3.0.2
    GIT_SHALLOW ON
    EXCLUDE_FROM_ALL
    SYSTEM)
FetchContent_MakeAvailable(SFML)

# ---- Subprojects ----
add_subdirectory(src/lib)
add_subdirectory(src/game)
add_subdirectory(src/editor)
