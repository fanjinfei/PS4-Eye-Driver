cmake_minimum_required(VERSION 3.0.2)

project(PS4-Eye-Driver)
include(package.cmake)

add_executable(PS4-Eye-Driver src/main.cpp src/ps4eye.cpp)
find_package(OpenCV REQUIRED)
target_link_libraries(PS4-Eye-Driver ${OpenCV_LIBS} libusb-1.0)

