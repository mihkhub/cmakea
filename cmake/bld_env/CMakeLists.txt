project(bld_env)

message(
"The path to the top level of the build tree: ${CMAKE_BINARY_DIR}")

add_executable(bld_env main.c)
