set(CMAKE_EXPORT_COMPILE_COMMANDS ON)

cmake_minimum_required(VERSION 3.20)

project(CGB VERSION 1.0
            DESCRIPTION "A C-based GameBoy emulator"
            LANGUAGES C)

file(GLOB_RECURSE cgb_src "src/*.c")

add_executable(cgb ${cgb_src})

find_package(raylib REQUIRED)

target_link_libraries(cgb PRIVATE raylib)
target_include_directories(cgb PRIVATE "include/")
target_compile_features(cgb PRIVATE c_std_99)
target_compile_options(cgb PRIVATE -Wall -Wextra -Wpedantic -O2)

