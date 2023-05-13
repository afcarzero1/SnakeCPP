cmake_minimum_required(VERSION 3.25)
project(MySnake)


set(CMAKE_CXX_STANDARD 17)

# Find ZeroMQ
find_package(PkgConfig REQUIRED)
pkg_check_modules(ZMQ REQUIRED libzmq)

add_executable(MySnake main.cpp)

# Link against ZeroMQ
target_link_libraries(MySnake ${ZMQ_LIBRARIES})
target_include_directories(MySnake PRIVATE ${ZMQ_INCLUDE_DIRS})



