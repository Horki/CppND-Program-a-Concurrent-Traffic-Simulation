cmake_minimum_required(VERSION 3.11.3)

project(traffic_simulation CXX)
set(CMAKE_CXX_FLAGS ${CMAKE_CXX_FLAGS} "-std=c++11 -pthread")

include(${CMAKE_BINARY_DIR}/conanbuildinfo.cmake)
conan_basic_setup()

# Find all executables
file(GLOB project_SRCS src/*.cpp)

# Add project executable
add_executable(${PROJECT_NAME} ${project_SRCS})
target_link_libraries(${PROJECT_NAME} ${CONAN_LIBS})
target_include_directories(${PROJECT_NAME}
  PUBLIC
  ${PROJECT_SOURCE_DIR}/include)
