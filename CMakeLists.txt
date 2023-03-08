cmake_minimum_required(VERSION 2.8)
project(plate)

find_package(OpenCV REQUIRED)
include_directories(${CMAKE_CURRENT_SOURCE_DIR}/sdk/include)

# add kafka
include_directories(${CMAKE_CURRENT_SOURCE_DIR}/include)
INCLUDE_DIRECTORIES(/usr/local/include/librdkafka)
LINK_DIRECTORIES(/usr/local/lib/)
link_directories(${CMAKE_CURRENT_SOURCE_DIR}/sdk/lib)

ADD_EXECUTABLE(plate main.cpp)
target_link_libraries(plate ${OpenCV_LIBS} libhcnetsdk.so libpthread.so)
target_link_libraries(plate rdkafka++ rdkafka jsoncpp)
