cmake_minimum_required(VERSION 3.20)

project(
    LearnVulkan 
    LANGUAGES CXX C
    DESCRIPTION "Learn Vulkan API"
    VERSION 0.1.0
)
add_subdirectory(vendor)
set(CMAKE_EXPORT_COMPILE_COMMANDS ON)

aux_source_directory(./src src_file)

message("Source files : ${src_file}")

add_executable(main ${src_file})
target_include_directories(main PRIVATE include)
target_compile_features(main PRIVATE cxx_std_17)
target_link_libraries(main PUBLIC glfw glad glm imgui)