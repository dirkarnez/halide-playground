cmake_minimum_required(VERSION 3.18)

project("halide-playground")

find_package(halide 19 EXACT REQUIRED) # PATHS "P:\\Downloads\\cpp-libraries\\portaudio\\build\\cmake\\portaudio")

if(halide_FOUND)
    message(STATUS "YES")
else()
    message(STATUS "NO")
endif()

add_executable(${PROJECT_NAME}
    "src/main.c"
)

target_link_libraries(${PROJECT_NAME} Halide::Halide Halide::Tools)
target_link_options(${PROJECT_NAME} PRIVATE "-static")
