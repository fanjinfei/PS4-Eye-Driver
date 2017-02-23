cmake_minimum_required(VERSION 3.0.2)

project(PS4-Eye-Driver)
include(package.cmake)

set (CMAKE_CXX_STANDARD 11)

include_directories("${CGET_INSTALL_DIR}/include/libusb-1.0")
add_executable(PS4-Eye-Driver src/main.cpp src/ps4eye.cpp)
find_package(OpenCV REQUIRED)
if(MSVC)
    target_link_libraries(PS4-Eye-Driver ${OpenCV_LIBS} libusb-1.0)
else()
    target_link_libraries(PS4-Eye-Driver ${OpenCV_LIBS} usb-1.0 pthread)
endif()
