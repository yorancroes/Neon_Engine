# Set the minimum CMake version and project name
cmake_minimum_required(VERSION 3.10)
project(MyPlace)

# Set the C standard
set(CMAKE_C_STANDARD 11)

# Add the executable
add_executable(MyPlace main.c 3rd_party/glad/src/glad.c)

# Find required libraries
find_package(OpenGL REQUIRED)
find_package(glfw3 REQUIRED)

# Link the libraries
target_include_directories(MyPlace PRIVATE 3rd_party/glad/include)
target_link_libraries(MyPlace PRIVATE OpenGL::GL glfw)
