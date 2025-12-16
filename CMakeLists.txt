cmake_minimum_required(VERSION 3.15)
project(gravity_sim LANGUAGES CXX)

set(CMAKE_CXX_STANDARD 17)
set(CMAKE_CXX_STANDARD_REQUIRED ON)

# Find packages provided by vcpkg
find_package(SDL2 CONFIG REQUIRED)
find_package(SDL2_image CONFIG REQUIRED)
find_package(OpenGL REQUIRED)
find_package(GLEW REQUIRED)
find_package(glfw3 CONFIG REQUIRED)

file(GLOB_RECURSE SRC_FILES
    "src/*.cpp"
    "src/*.h"
)

add_executable(gravity_sim ${SRC_FILES})

target_link_libraries(gravity_sim
    PRIVATE
        SDL2::SDL2
        SDL2::SDL2main
        SDL2_image::SDL2_image
        OpenGL::GL
        GLEW::GLEW
        glfw
)
