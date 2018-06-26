# CMake minimum version
cmake_minimum_required (VERSION 3.6)

# Project Name
project (MainProject)

# Get OpenGL Libraries
find_package(OpenGL REQUIRED)

# GLFW PATHS
include_directories(${CMAKE_SOURCE_DIR}/../External-Libraries/GLFW/include)
link_directories(${CMAKE_SOURCE_DIR}/../External-Libraries/GLFW/lib-vc2015)

# GLEW PATHS
include_directories(${CMAKE_SOURCE_DIR}/../External-Libraries/GLEW/include)
link_directories(${CMAKE_SOURCE_DIR}/../External-Libraries/GLEW/lib/Release/Win32)

set(MY_HEADER_FILES
	#../Headers/stb_image.h
)

set(MY_SOURCE_FILES
	../Source/main.cpp
)

add_executable(index
	${MY_HEADER_FILES}
	${MY_SOURCE_FILES}
)
target_link_libraries(MainProject
	${OPENGL_LIBRARY}
	glfw3
	glew32s
)