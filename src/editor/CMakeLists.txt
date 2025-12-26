add_executable(editor main.cpp)
target_link_libraries(editor PRIVATE red-panda)

if (MSVC)
    set(CMAKE_MSVC_RUNTIME_LIBRARY "MultiThreaded$<$<CONFIG:Debug>:Debug>")
endif()

target_compile_features(red-panda PRIVATE cxx_std_17)
