cmake_minimum_required (VERSION 2.8)
project (simple)


find_package(PkgConfig REQUIRED)
find_package(OpenGL REQUIRED)
pkg_search_module(GLFW REQURED glfw3)

include_directories(${GLFW_INCLUDE_DIRS})

add_executable(simple 
	main.cpp
	)

target_link_libraries(simple 
	${OPENGL_LIBRARY}
	${GLFW_LIBRARIES}
	)



