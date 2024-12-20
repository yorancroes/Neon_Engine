cmake_minimum_required(VERSION 3.10)

project(MyPlace)

# Add the src and glad directories to the include path
include_directories(${PROJECT_SOURCE_DIR}/src)
include_directories(${PROJECT_SOURCE_DIR}/3rd_party/glad/include)  # Correct path to glad headers

# Automatically add all .c files in the src directory
file(GLOB SOURCES "src/*.c")

# Add glad.c to the list of source files
list(APPEND SOURCES "${PROJECT_SOURCE_DIR}/3rd_party/glad/src/glad.c")

# Create the executable from all the source files
add_executable(MyPlace ${SOURCES})

# Link with OpenGL and GLFW libraries
find_package(OpenGL REQUIRED)
find_package(glfw3 REQUIRED)

target_link_libraries(MyPlace OpenGL::GL glfw)

