cmake_minimum_required(VERSION 3.31)

project(
    ExampleProject
    VERSION 1.0
    LANGUAGES CXX
)

#Extern dependencies
add_subdirectory(extern)

file(GLOB_RECURSE SOURCES "${ExampleProject_SOURCE_DIR}/ExampleProject/*.cpp")
add_executable(ExampleExecutable ${SOURCES})
target_include_directories(ExampleExecutable PUBLIC "${ExampleProject_SOURCE_DIR}/ExampleProject")
target_compile_features(ExampleExecutable PUBLIC cxx_std_17)
target_link_libraries(ExampleExecutable PUBLIC imgui glfw glad)