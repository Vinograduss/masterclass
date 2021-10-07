# masterclass
Мастеркласс по созданию проектов на С/С++

## Подготовка
Для мастеркласса на компе должен быть установлен:
1. **компилятор gcc** (clang на mac os)
   
   проверить установлен ли gcc можно с помощью команды `gcc --version`
2. **cmake**

   его можно поставить через `apt-get install cmake`, `brew install cmake`, более полная инструкция: https://cmake.org/install/
3. **Google test**
   
   https://github.com/google/googletest/blob/master/googletest/README.md

## Мастеркласс
В рамках мастеркласса мы научимся стоить приложения на С/С++ и добавлять к ним тесты

1. [Собираем проект вручную](https://github.com/Vinograduss/masterclass/blob/main/build_with_hand.md)
2. [Собираем с помощью Makefile](https://github.com/Vinograduss/masterclass/blob/main/build_with_make.md)
3. [Cобираем с помощью Cmake](https://github.com/Vinograduss/masterclass/blob/main/build_with_cmake.md)
4. [Добавляем тесты Google Test](https://github.com/Vinograduss/masterclass/blob/main/test.md)
