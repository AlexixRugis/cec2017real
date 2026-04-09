cmake_minimum_required(VERSION 3.15)
project(cec17)
set(CMAKE_C_FLAGS   "${CMAKE_C_FLAGS} -O2")
set(CMAKE_CXX_FLAGS "${CMAKE_CXX_FLAGS} -O2")
add_executable(cec17_test "test.cc")
add_executable(cec17_testrandom "testrandom.cc")
add_executable(cec17_testsolis "testsolis.cc")
add_library(cec17_test_func "cec17_test_func.c" "cec17.c" "cec17.h")
target_include_directories(cec17_test_func PUBLIC 
    ${CMAKE_CURRENT_SOURCE_DIR}
)
target_link_libraries(cec17_test cec17_test_func)
target_link_libraries(cec17_testrandom cec17_test_func)
target_link_libraries(cec17_testsolis cec17_test_func)
