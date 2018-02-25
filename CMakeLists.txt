
cmake_minimum_required(VERSION 3.5)

project(Spooky C)

set(CMAKE_POSITION_INDEPENDENT_CODE TRUE)
set(CMAKE_C_FLAGS_RELEASE "-O3")
set(CMAKE_C_FLAGS_DEBUG "-g")
set(CMAKE_C_FLAGS   "${CMAKE_C_FLAGS} -march=native")

add_library(
  spookyhash
  spookyhash.c
  )

add_executable(
  spookyhash-test
  spookyhash-test.c
  )

target_link_libraries(
  spookyhash-test
  spookyhash
  ${CMAKE_THREAD_LIBS_INIT}
)
