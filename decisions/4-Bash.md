task1 - Скриптуем по полной
1. Шебанг (#!) — первая строка скрипта, указывает интерпретатор.
#!/bin/bash

2. Расширение исполняемого файла — НЕ обязательно. Главное:

Шебанг в первой строке
Права на выполнение: chmod +x файл
Можно запускать: ./script

3. Скрипт для автоматизации работы с файлами:
```
!/bin/bash

set -euo pipefail

#3.1 Создание папок

mkdir -p test_dir/sub1/sub2

echo "Папки созданы"

#3.2 Создание файла с текстом
echo "Пример текста" > test_dir/file1.txt
echo "Второй файл" > test_dir/file2.txt

#3.3 Вывод списка файлов
echo "Содержимое test_dir:"
ls -la test_dir/

#3.4 Копирование файла
cp test_dir/file1.txt test_dir/copy_file1.txt

#3.5 Переименование файла
mv test_dir/file2.txt test_dir/renamed_file.txt

#3.6 Сравнение файлов
echo "Сравнение оригинал/копия:"
diff test_dir/file1.txt test_dir/copy_file1.txt || echo "Файлы идентичны"

#3.7 Сортировка содержимого
echo -e "3\n1\n2" > test_dir/numbers.txt
sort test_dir/numbers.txt > test_dir/sorted_asc.txt
sort -r test_dir/numbers.txt > test_dir/sorted_desc.txt

echo "Результаты сортировки:"
cat test_dir/sorted_asc.txt
cat test_dir/sorted_desc.txt

#3.8 Показать права доступа
echo "Права доступа:"
ls -l test_dir/

#3.9 Удаление
echo "Удаление тестовой папки..."
rm -rf test_dir

```
Флаги.
-e — выход при первой ошибке (прерывает скрипт)
-u — ошибка при обращении к необъявленной переменной
-o pipefail — код возврата пайплайна = коду последней неудачной команды в цепочке

