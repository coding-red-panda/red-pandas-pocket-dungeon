add_executable(editor main.cpp)
target_link_libraries(editor PRIVATE red-panda)
target_compile_features(red-panda PRIVATE cxx_std_17)
