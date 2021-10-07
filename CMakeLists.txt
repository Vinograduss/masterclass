project(test)

set(CMAKE_CXX_STANDARD 11)
set(CMAKE_CXX_STANDARD_REQUIRED ON)

set(LIB_SOURCE_FILES fib.cpp)
add_library(fib STATIC ${LIB_SOURCE_FILES})

add_executable(main main.cpp)
target_link_libraries(main fib)