## C

#### Полезные библиотеки
```c
#include <errno.h> // errno (переменная для кода ошибки), ...
#include <float.h> // FLT_EPSILON, DBL_EPSILON, LDBL_EPSILON, ...
#include <limits.h> // CHAR_MAX, INT_MAX, UINT_MAX, LLONG_MIN, ... 
#include <stdint.h> // int8_t, int_16t, uint16_t, uintptr_t, ...
#include <stdio.h> // EOF, getchar, putchar,  ... 
#include <stdlib.h> // malloc, calloc, realloc, free, ...
#include <string.h> // strerror, ...
```
#### Полезные флаги компиляции

* `-o file` &mdash; запись результата в file
* `-ftrapv` &mdash; abort() при знаковом целочисленном переполнении
* `-fsanitize=undefined` &mdash; проверка на UB при работе программы

#### Ввод и вывод 

Прототипы функций:
```c
#include <stdio.h> 

int getchar(void);
int putchar(int);
int scanf(const char *format, ... );
int printf(const char *format, ...); 
```

В коде программы символьные константы заключаются в одинарные кавычки  `'`<br> 
Специальные символы
 * `'\n'` - символ перевода новой строки,
 * `'\r'` - символ возврата каретки,
 * `'\t'` - символ табуляции,
 * `'\b'` - символ забоя (backspace), 
 * `'\\'` - собственно, символ обратной косой черты,
 * `'\''` - одинарная кавычка (апостроф),
 * `'\"'` - двойная кавычка.

Структура 

Спецификаторы для `scanf`

TODO

Спецификаторы для `printf`

TODO

#### Строки в C

В конце строки находится байт `\0` (признак конца строки).<br>

#### Аргументы командой строки

```c
int main(int argc, char* argv[]) {}
```

`argc` - число аргументов
`argv` - массив указателей на строки

`argv[0]` - это имя программы, которое использовалось в командной строке запуска

#### Файлы

```c
FILE *f = fopen(argv[1], "r");
if (!f) {
    fprintf(stderr, "fopen failed: %s\n", strerror(errno));
    exit(EXIT_FAILURE);
}
fclose(f);
```

#### Обработка ошибок

```c
fprintf(stderr, "!!!error!!!\n");
// в случае ошибки должен быть ненулевой код завершения
// константа EXIT_FAILURE равна 1
exit(EXIT_FAILURE);
```
