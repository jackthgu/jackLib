cmake_minimum_required (VERSION 2.8)
project (simple)

find_package(PkgConfig REQUIRED)
find_package(OpenGL REQUIRED)
pkg_search_module(GLFW REQURED glfw3)


set(JACKLIB_DEP_DIR ${CMAKE_SOURCE_DIR}/../dep/)

message("hey")
message(${JACKLIB_DEP_DIR})

include_directories(
	.
	${GLFW_INCLUDE_DIRS}
	${JACKLIB_DEP_DIR}
	)

add_executable(simple 
	main.cpp
	)

add_library(GLAD "${JACKLIB_DEP_DIR}/glad/glad.c")
set(LIBS ${LIBS} GLAD)
set(LIBS ${LIBS} 
	dl
	m
	pthread)


link_directories(
	)

target_link_libraries(simple 
	${OPENGL_LIBRARY}
	${GLFW_LIBRARIES}
	${LIBS}
	)



