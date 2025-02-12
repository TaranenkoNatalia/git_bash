# 📟 Работа с git и bash

В рамках курса работала с базовыми командами Bash: создавала, перемещала и удаляла файлы и папки, редактировала содержимое, выполняла поиск, работала с процессами и API. Этот опыт помог мне лучше понять работу с командной строкой и управлением файлами в терминале.  

Ниже представлено мое решение:

## Задача 1

##### Основные операции с файлами и директориями в Bash
```bash
cd                                    # Открыть домашнюю директорию через терминал
pwd                                   # Определить имя папки, в которой вы находитесь
mkdir test1                           # Создать внутри этой папки каталог с именем test1
cd test1                              # Перейти в папку test1
touch 1.txt 2.txt 3.txt               # Создать файл 1,2 и 3 внутри каталога test1
ls                                    # Проверить содержимое каталога test1
cd                                    # Перейти в домашнюю директорию
mkdir test2                           # Создать папку test2 внутри домашней директории 
rmdir test2                           # Удалить папку test2
rm test1/2.txt                        # Удалить файл 2 из папки test1
mkdir test3                           # Создать папку в домашней директории test3 и добавить в нее два файла
cd test3
touch 1.txt 2.txt
cd                                    # Удалить папку test3
rm -r test3
mkdir test4                           # Создать папку test4 в домашней директории
mv test1/1.txt test1/3.txt test4      # Переместить файлы 1 и 3 из папки test1 в папку test4
cd test4                              # Добавить в файл 1 три строки со словами line
echo line >> 1.txt
echo line >> 1.txt
echo line >> 1.txt
cat 1.txt                             # Посмотреть содержимое файла 1
echo line >> 3.txt                    # Добавьте в файл 3 три строки со словами line
echo line >> 3.txt
echo line >> 3.txt
cat 1.txt 3.txt                       # Просмотрите содержимое двух файлов (1 и 3) сразу                   
nano 1.txt                            # Используя один из редакторов замените все строки в файле 1
^\
Search: line
Replace with: circle
A (All)
^O 
Enter 
^X

```
## Задача 2
##### Работа с файлами, текстовым поиском, процессами и API-запросами в Bash
```bash
cd                                            # Зайти в домашнюю директорию через терминал
mkdir test3                                   # Создать папку test 3 
echo -e "row1\nrow2\nrow3\nrow4" > 4.txt      # Добавить в папку test 3 три файла 4, 5 и 6, 
echo -e "row1\nrow2\nrow3\nrow4" > 5.txt      # в каждом из которых должно быть по 4 строки row1, row2, row3, row4
echo -e "row1\nrow2\nrow3\nrow4" > 6.txt
grep "row2" 5.txt                             # Найдите строку row2 в файле 5
grep -r "row"                                 # Найдите строку row в папке test3
grep -c "row" 6.txt                           # Посчитайте сколько строк с содержимым row в файле 6
find 5.txt                                    # Найдите файл 5 внутри папки test3
echo "test" >> 4.txt                          # Используя команду echo, добавьте слово test в файл 4
sed -i 's/test/fail/g' 4.txt                  # Замените слово test в файле 4 на fail
echo "test" >> 4.txt                          # Добавьте в файл 4 слово test так, чтобы сохранилось содержимое
ps aux                                        # Просмотрите все процессы для юзеров, которые происходят в системе
kill 666                                      # Убейте процесс 666 в консоли 
ping rusau.net                                # Узнайте доступность ресурса rusau.net, используя ping
ping -c 5 rusau.net                           # Отправьте 5 пакетов на сайт rusau.net

# Используя GET и команду curl, получите информацию о зарегистрированных питомцах
 #с любым статусом на https://petstore.swagger.io/findByStatus?status=registered
curl https://petstore.swagger.io/v2/pet/findByStatus?status=available

# Используя POST и команду curl, создайте нового пользователя на https://petstore.swagger.io/
curl -X 'POST' \                                                     
  'https://petstore.swagger.io/v2/user/createWithList' \
  -H 'accept: application/json' \
  -H 'Content-Type: application/json' \
  -d '[
  {
    "id": 0,
    "username": "aki",
    "userStatus": 0
  }
]'

```
