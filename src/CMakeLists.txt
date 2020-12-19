add_library(Example
    SHARED Example.cpp
)

target_include_directories(Example
  PUBLIC . 
)