cmake_minimum_required (VERSION 2.8)
project (simple)

find_package(PkgConfig REQUIRED)
find_package(OpenGL REQUIRED)
pkg_search_module(GLFW REQURED glfw3)

message(${CMAKE_SOURCE_DIR})

include_directories(
	.
	${CMAKE_SOURCE_DIR}/glad/build/include
	${GLFW_INCLUDE_DIRS}
	)

add_executable(simple 
	main.cpp
	)

link_directories(
	)

target_link_libraries(simple 
	${OPENGL_LIBRARY}
	${GLFW_LIBRARIES}
	${CMAKE_SOURCE_DIR}/glad/build/libglad.a
	dl
	m
	pthread
	)



