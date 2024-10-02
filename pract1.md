# Практическое занятие №1. Введение, основы работы в командной строке

П.Н. Советов, РТУ МИРЭА

Научиться выполнять простые действия с файлами и каталогами в Linux из командной строки. Сравнить работу в командной строке Windows и Linux.

## Задача 1
Вывести отсортированный в алфавитном порядке список имен пользователей в файле passwd (вам понадобится grep).

grep '.*' /etc/passwd | cut -d: -f1 | sort

![Photo_1](https://github.com/user-attachments/assets/aaab04a3-bfdc-4299-a005-4b78ff15225a)


## Задача 2

awk '{print $2, $1}' /etc/protocols | sort -nr | head -n 5

![изображение](https://github.com/user-attachments/assets/f7cd5921-5632-4914-8e9d-a3f1c50de9ba)


## Задача 3

#!/bin/bash
text=$*
length=${#text}
for _ in $(seq 1 $((length + 2))); do
    line+="-"
done
echo "+${line}+"
echo "| ${text} |"
echo "+${line}+"

![изображение](https://github.com/user-attachments/assets/e7ddd073-e1c3-4f6a-afbc-7d8a29639428)


Перед отправкой решения проверьте его в ShellCheck на предупреждения.

## Задача 4

Написать программу для вывода всех идентификаторов (по правилам C/C++ или Java) в файле (без повторений).

Пример для hello.c:

```
h hello include int main n printf return stdio void world
```

## Задача 5

#!/bin/bash
file=$1
chmod 755 "./$file"
sudo cp "$file" /usr/local/bin/
echo "compleat"

![изображение](https://github.com/user-attachments/assets/6a6a0446-583d-4456-8857-42c17a0cb4fa)


В результате для banner задаются правильные права доступа и сам banner копируется в /usr/local/bin.

## Задача 6

Написать программу для проверки наличия комментария в первой строке файлов с расширением c, js и py.

## Задача 7

Написать программу для нахождения файлов-дубликатов (имеющих 1 или более копий содержимого) по заданному пути (и подкаталогам).

## Задача 8

Написать программу, которая находит все файлы в данном каталоге с расширением, указанным в качестве аргумента и архивирует все эти файлы в архив tar.

## Задача 9

Написать программу, которая заменяет в файле последовательности из 4 пробелов на символ табуляции. Входной и выходной файлы задаются аргументами.

## Задача 10

Написать программу, которая выводит названия всех пустых текстовых файлов в указанной директории. Директория передается в программу параметром. 

## Полезные ссылки

Линукс в браузере: https://bellard.org/jslinux/

ShellCheck: https://www.shellcheck.net/

Разработка CLI-приложений

Общие сведения

https://ru.wikipedia.org/wiki/Интерфейс_командной_строки
https://nullprogram.com/blog/2020/08/01/
https://habr.com/ru/post/150950/

Стандарты

https://www.gnu.org/prep/standards/standards.html#Command_002dLine-Interfaces
https://www.gnu.org/software/libc/manual/html_node/Argument-Syntax.html
https://pubs.opengroup.org/onlinepubs/9699919799/basedefs/V1_chap12.html

Реализация разбора опций

Питон

https://docs.python.org/3/library/argparse.html#module-argparse
https://click.palletsprojects.com/en/7.x/
