cmake_minimum_required(VERSION 3.5)
project(cpp_server)


find_package(Boost REQUIRED COMPONENTS system thread)
include_directories(${Boost_INCLUDE_DIRS})
set(CMAKE_CXX_FLAGS "${CMAKE_CXX_FLAGS} -std=c++11")

file(GLOB SOURCE_FILES "*.cpp" "*.h"  "*.cc")

add_executable(cpp_server ${SOURCE_FILES})
set(CMAKE_BUILD_TYPE Debug)

target_link_libraries(cpp_server ${Boost_SYSTEM_LIBRARY} ${Boost_THREAD_LIBRARY} ${Boost_LIBRARIES} ${CMAKE_THREAD_LIBS_INIT})