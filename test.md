1. Редактируем СMakeLists.txt, добавляем GTest
```
cmake_minimum_required(VERSION 3.16)

project(test)

set(CMAKE_CXX_STANDARD 11)
set(CMAKE_CXX_STANDARD_REQUIRED ON)

set(LIB_SOURCE_FILES fib.cpp)
add_library(fib STATIC ${LIB_SOURCE_FILES})

add_executable(main main.cpp)
target_link_libraries(main fib)

enable_testing()
find_package(GTest REQUIRED)

include_directories(${GTEST_INCLUDE_DIRS})
add_executable(fib_test fib_test.cpp)
target_link_libraries(fib_test ${GTEST_LIBRARIES} fib)
```
2. Создаем файл с тестом `fib_test.cpp`
```
#include <gtest/gtest.h>
#include "fib.h"


TEST(FIB_TEST, Assert_1) {
  EXPECT_EQ(fib(1), 1);
}

TEST(FIB_OPT_TEST, Assert_1) {
  EXPECT_EQ(fib_opt(1), 1);
}

TEST(FIB_TEST, Compare_20) {
  EXPECT_EQ(fib(20), fib_opt(20));
}

int main(int argc, char **argv) {
  ::testing::InitGoogleTest(&argc, argv);
  return RUN_ALL_TESTS();
}
```

3. Cобираем проект в папке build

   `make`
   
4. Запускаем

   `./fib_test`
6. Видим, что тетсты прошли
```
[==========] Running 3 tests from 2 test suites.
[----------] Global test environment set-up.
[----------] 2 tests from FIB_TEST
[ RUN      ] FIB_TEST.Assert_1
[       OK ] FIB_TEST.Assert_1 (0 ms)
[ RUN      ] FIB_TEST.Compare_20
[       OK ] FIB_TEST.Compare_20 (0 ms)
[----------] 2 tests from FIB_TEST (0 ms total)

[----------] 1 test from FIB_OPT_TEST
[ RUN      ] FIB_OPT_TEST.Assert_1
[       OK ] FIB_OPT_TEST.Assert_1 (0 ms)
[----------] 1 test from FIB_OPT_TEST (0 ms total)

[----------] Global test environment tear-down
[==========] 3 tests from 2 test suites ran. (1 ms total)
[  PASSED  ] 3 tests.
```
