add_executable(game main.cpp)
target_link_libraries(game PRIVATE red-panda)
target_compile_features(game PRIVATE cxx_std_17)
