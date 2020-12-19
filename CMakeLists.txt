cmake_minimum_required(VERSION 3.0)

project(GTestProject)

enable_language(CXX)
set(CMAKE_CXX_STANDARD 14) # C++14...
set(CMAKE_CXX_STANDARD_REQUIRED ON) #...is required...
set(CMAKE_CXX_EXTENSIONS OFF) #...without compiler extensions like gnu++11

set(EXTERNAL_INSTALL_LOCATION ${CMAKE_BINARY_DIR}/external)

include(ExternalProject)
include(${PROJECT_SOURCE_DIR}/vendor/google-test/google-test.cmake)


include_directories(${EXTERNAL_INSTALL_LOCATION}/include)
link_directories(${EXTERNAL_INSTALL_LOCATION}/lib)


add_subdirectory(src)
add_subdirectory(test)

add_executable(FirstTest Main.cpp)

#add_dependencies(FirstTest googletest)
#target_link_libraries(FirstTest gtest gtest_main pthread)