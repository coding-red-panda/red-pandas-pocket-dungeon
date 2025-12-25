add_library(red-panda main.cpp)
target_include_directories(red-panda PUBLIC ${CMAKE_CURRENT_SOURCE_DIR})
target_compile_features(red-panda PRIVATE cxx_std_17)

# Link against SFML so our library is aware of SFML.
# We need to public link so the executables can access SFML headers.
target_link_libraries(red-panda
    PUBLIC
        SFML::Graphics
        SFML::Audio
)
