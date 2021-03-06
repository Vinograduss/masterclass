# Написание программ на СИ/С++

## Компиляция вручную
1. создаем файл main.cpp
2. пишем  в нем программу Hello World

```
#include <iostream>

int main()
{
	std::cout << "Hello world " << std::endl;;
	return 0;
}
```
3) собираем наш проект, в терминале вводим 
```bash
g++  main.cpp
```
4) смотрим список файлов в директории - ls
`main.cpp a.out`

5) запускаем бинарник
  `./a.out`

6) создаем файлик с реализаций вычисления чисел фибоначи fib.cpp
```c++
int fib(int n)
{
    if (n == 0 || n == 1)
        return n;

    return fib(n - 1) + fib (n - 2);
}

int fib_opt(int n)
{
	if (n == 0 || n == 1)
        return n;

    int prev = 1;
    int cur = 1;

    for (int i = 2; i < n; i++)
    {
    	int res = prev + cur;
    	prev = cur;
    	cur = res;
    }

    return cur;
}

```

7) создаем файлик с объявлениями функций fib.h
```c++
 #pragma once

int fib(int n);
int fib_opt(int n);
 ```

 8) включаем этот файл в main.cpp и добавляем использование функций
 ```c++
 #include "fib.h"

.... 
 	std::cout << fib(5) << std::endl;
	std::cout << fib_opt(5) << std::endl;
 ```
 9) компилируем 
 ```
 g++ main.cpp fib.cpp
 ```

 ## Makefile
 1) Создаем файл
 Makefile

 2) Переносим описание процесса компиляции в файл Makefile
 build:
	g++ main.cpp fib.cpp

3) Разносим процесс компиляции двух сущностей в Makefile
```

build: fib.o
	g++ main.cpp fib.o -o main.exe

fib.o: fib.cpp
	g++ -c fib.cpp -o fib.o
```
4) проверяем
./main.exe

## CMake

## Test