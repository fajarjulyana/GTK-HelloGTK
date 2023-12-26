cmake_minimum_required(VERSION 3.10)
project(HelloGTK)

set(CMAKE_C_STANDARD 11)

find_package(PkgConfig REQUIRED)
pkg_check_modules(GTK3 REQUIRED gtk+-3.0)

include_directories(${GTK3_INCLUDE_DIRS})
link_directories(${GTK3_LIBRARY_DIRS})

add_definitions(${GTK3_CFLAGS_OTHER})

add_executable(HelloGTK main.c)
target_link_libraries(HelloGTK ${GTK3_LIBRARIES})

# Tambahkan baris ini
configure_file(${CMAKE_SOURCE_DIR}/background.png ${CMAKE_CURRENT_BINARY_DIR}/background.png COPYONLY)
