add_executable(game main.cpp)
target_link_libraries(game PRIVATE red-panda)

if (MSVC)
    set(CMAKE_MSVC_RUNTIME_LIBRARY "MultiThreaded$<$<CONFIG:Debug>:Debug>")
endif()

target_compile_features(game PRIVATE cxx_std_17)