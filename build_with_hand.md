# Компиляция проекта вручную
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
4) проверяем список файлов в директории - `ls`
   
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

 8) подключаем его в main.cpp и добавляем вызов функций
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
