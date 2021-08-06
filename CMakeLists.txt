cmake_minimum_required(VERSION 3.1)

project(binstream)

add_library(${PROJECT_NAME} INTERFACE "${CMAKE_CURRENT_SOURCE_DIR}/include/binstream/binstream.h")
target_include_directories(${PROJECT_NAME} INTERFACE "${CMAKE_CURRENT_SOURCE_DIR}/include")
set_target_properties(${PROJECT_NAME} PROPERTIES CXX_STANDARD 11)

add_executable(${PROJECT_NAME}_test "src/${PROJECT_NAME}_test.cpp")
target_link_libraries(${PROJECT_NAME}_test ${PROJECT_NAME})
set_target_properties(${PROJECT_NAME}_test PROPERTIES CXX_STANDARD 11)

add_executable(${PROJECT_NAME}_bench "src/${PROJECT_NAME}_bench.cpp")
target_link_libraries(${PROJECT_NAME}_bench ${PROJECT_NAME})
set_target_properties(${PROJECT_NAME}_bench PROPERTIES CXX_STANDARD 11)

