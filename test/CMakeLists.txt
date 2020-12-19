cmake_minimum_required(VERSION 3.18)

set(This ExampleTests)

set(Sources
    ExampleTests.cpp
)

add_executable(
    ${This} ${Sources}
)

target_link_libraries(${This} 
    gtest 
    gtest_main 
    pthread
    Example
)

add_test( PUBLIC
    NAME ${This}
    COMMAND ${This}
)