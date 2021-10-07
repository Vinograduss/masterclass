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