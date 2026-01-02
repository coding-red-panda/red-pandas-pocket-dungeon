cmake_minimum_required(VERSION 3.28)
project(red-pandas-pocket-dungeon LANGUAGES CXX)

# Set output directories
# executables
set(CMAKE_RUNTIME_OUTPUT_DIRECTORY ${CMAKE_BINARY_DIR}/bin)
# static libraries
set(CMAKE_ARCHIVE_OUTPUT_DIRECTORY ${CMAKE_BINARY_DIR}/lib)
# shared libraries
set(CMAKE_LIBRARY_OUTPUT_DIRECTORY ${CMAKE_BINARY_DIR}/bin)

include(FetchContent)

# ---- SFML static build options ----
set(SFML_BUILD_SHARED_LIBS OFF CACHE BOOL "" FORCE)
set(SFML_STATIC_LIBRARIES ON CACHE BOOL "" FORCE)

# Optional: disable what you don't need
set(SFML_BUILD_NETWORK OFF CACHE BOOL "" FORCE)

# Download and build SFML from source.
FetchContent_Declare(SFML
    GIT_REPOSITORY https://github.com/SFML/SFML.git
    GIT_TAG 3.0.2
    GIT_SHALLOW ON
    EXCLUDE_FROM_ALL
    SYSTEM)
FetchContent_MakeAvailable(SFML)

# Download and build json for C++ (using release source to keep size down)
FetchContent_Declare(JSON URL https://github.com/nlohmann/json/releases/download/v3.12.0/json.tar.xz)
FetchContent_MakeAvailable(JSON)

# ---- Subprojects ----
add_subdirectory(src/lib)
add_subdirectory(src/game)
add_subdirectory(src/editor)
