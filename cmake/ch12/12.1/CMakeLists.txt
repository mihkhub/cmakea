cmake_minimum_required( VERSION 2.6)

project (Tutorial)
add_library(m tutorial.cpp)
add_executable(Tutorial tutorial.cpp)

enable_testing()

# does the application run
add_test(TutorialRuns Tutorial 25)

# does the usage message work?
add_test(TutorialUsage Tutorial)
set_tests_properties( TutorialUsage
PROPERTIES
PASS_REGULAR_EXPRESSION "Usage:.*number")
