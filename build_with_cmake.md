1. Создаем файл
`tourch CMakeLists.txt`

2. Добавляем информацию о сборке проекта
```
project(test)

add_executable(main main.cpp fib.cpp)
```
3. Создаем директорию для вспомогательных файлов

   `mkdir build`
   
4. Переходим в директорию конфигурируем проект

   `cmake ..`

5. Собираем  проект

   `make -j2`
6. Смотрим список файлов в директории

   `ls`
  
7. Запускаем exe

   `./main`

8. Выносим вычислений фибоначчи  в библиотеку
```
project(test)

set(CMAKE_CXX_STANDARD 11)
set(CMAKE_CXX_STANDARD_REQUIRED ON)

set(LIB_SOURCE_FILES fib.cpp)
add_library(fib STATIC ${LIB_SOURCE_FILES})

add_executable(main main.cpp)
target_link_libraries(main fib)
```
9. Пересобираем проект

   `cmake ..`

   `make -j2`
10. Смотрим список файлов

    `ls` 
    
    и замечаем что кроме `exe` файла появилась статическая библиотека `libfib.a`
