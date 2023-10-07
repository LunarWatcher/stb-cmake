cmake_minimum_required(VERSION 3.21)
project(stb-cmake VERSION 1.0.0 DESCRIPTION "Stb build for CMake with FetchContent")

option(STB_TAG "Upstream ref for stb" "master")

include(FetchContent)
FetchContent_Declare(stb-source
    GIT_REPOSITORY https://github.com/nothings/stb
    GIT_TAG ${STB_TAG})
FetchContent_MakeAvailable(stb-source)

add_library(stb INTERFACE)
target_include_directories(stb INTERFACE ${stb-source_SOURCE_DIR})

add_library(stb::stb ALIAS stb)

if (PROJECT_IS_TOP_LEVEL)
    add_subdirectory(test)
endif()
