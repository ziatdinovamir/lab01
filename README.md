## Laboratory work I

Данная лабораторная работа посвещена изучению утилит для разработки проектов


## Tutorial

создаем переменную окружения с именем GITHUB_USERNAME и GIST_TOKEN и присваем им значения. 

```bash
$ export GITHUB_USERNAME=ziatdinovamir
$ export GIST_TOKEN=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
$ alias edit=nano
```
создаем директорию, переходим в нее и выводим пусть к ней.

```sh
$ mkdir -p ${GITHUB_USERNAME}/workspace
$ cd ${GITHUB_USERNAME}/workspace
$ pwd
```

/home/amir/ziatdinovamir/workspace

также можно перейти на уровень выше и вывести ее путь

```sh
$ cd ..
$ pwd
```
/home/amir/ziatdinovamir

```sh
$ mkdir -p workspace/tasks/
$ mkdir -p workspace/projects/
$ mkdir -p workspace/reports/
$ cd workspace
```
Создаем несколько каталогов и переходим в каталог workspace. Будет создана структура каталогов:

workspace/

├── tasks/

├── projects/

└── reports/

```sh
# Debian
$ wget https://nodejs.org/dist/v6.11.5/node-v6.11.5-linux-x64.tar.xz
$ tar -xf node-v6.11.5-linux-x64.tar.xz
$ rm -rf node-v6.11.5-linux-x64.tar.xz
$ mv node-v6.11.5-linux-x64 node
```
После данных команд в текущей директории останется папка node, которая содержить распакованную версию Node.js. Затем выводим каталога node/bin.

```sh
$ ls node/bin
$ echo ${PATH}
```
Добавляем путь и выводим обновленное значение.

```sh
$ export PATH=${PATH}:`pwd`/node/bin
$ echo ${PATH}
```

```sh
$ mkdir scripts
$ cat > scripts/activate<<EOF
export PATH=\${PATH}:`pwd`/node/bin
EOF
$ source scripts/activate
```
Устанавливаем gist

```sh
$ gem install gist
```
Устанавливаем права на записьв скрытый файл токен

```sh
$ (umask 0077 && echo ${GIST_TOKEN} > ~/.gist)
```
Создаем папку с копией лабораторной работы, редайктируем его в редакторе и отправляем.

```sh
$ export LAB_NUMBER=01
$ git clone https://github.com/tp-labs/lab${LAB_NUMBER} tasks/lab${LAB_NUMBER}
$ mkdir reports/lab${LAB_NUMBER}
$ cp tasks/lab${LAB_NUMBER}/README.md reports/lab${LAB_NUMBER}/REPORT.md
$ cd reports/lab${LAB_NUMBER}
$ edit REPORT.md
$ gist REPORT.md
```


## Homework

1. Скачиваем библиотеку *boost*: 
```sh
$ wget https://sourceforge.net/projects/boost/files/boost/1.69.0/boost_1_69_0.tar.gz
```
2. Разархивируем скаченный файл в директорию `~/boost_1_69_0`
```sh
tar -xf boost_1_69_0.tar.gz
```
3. Подсчитываем количество файлов в директории `~/boost_1_69_0` **не включая** вложенные директории.
```sh
$ find ~/boost_1_69_0 -maxdepth 1 -type f | wc -l
-maxdepth 1 - не заходить в подпапки
-type f - искать только файлы
wc -l - подсчет количества файлов
```
Программа выдала значение 16 файлов
4. Подсчитываем количество файлов в директории `~/boost_1_69_0` **включая** вложенные директории.
```sh
$ find ~/boost_1_69_0 -type f | wc -l
```
Почти та же команда, только без захода в подпапки.
ППрограмма выдала значение 16 файлов
5. 1)Подсчитываем количество заголовочных файлов
```sh
$ find ~/boost_1_69_0 -type f \( -name "*.h" -o -name "*.hpp" -o -name "*.hxx" \) | wc -l
-name "*.h" — имя файла заканчивается на .h.
-o — логическое ИЛИ 
-name "*.hpp" — имя файла заканчивается на .hpp.
-name "*.hxx" — имя файла заканчивается на .hxx.
```
Программа выдала значение 15208 файлов
2) Файлов с расширением `.cpp`
```sh
$ find ~/boost_1_69_0 -type f -name "*.cpp" | wc -l
```
3) Сколько остальных файлов (не заголовочных и не `.cpp`).
```sh
$ find ~/boost_1_69_0 -type f ! \( -name "*.h" -o -name "*.hpp" -o -name "*.hxx" -o -name "*.cpp" \) | wc -l
```
То есть прописываем ту же команду, что в пункте 1, то перед скобками ставим !, что означает НЕ
6. Найдем полный пусть до файла `any.hpp` внутри библиотеки *boost*.
```sh
$ find ~/boost_1_69_0 -type f -name "any.hpp"
```
Ответ: 
```sh
/home/amir/boost_1_69_0/boost/any.hpp
/home/amir/boost_1_69_0/boost/fusion/include/any.hpp
/home/amir/boost_1_69_0/boost/fusion/algorithm/query/detail/any.hpp
/home/amir/boost_1_69_0/boost/fusion/algorithm/query/any.hpp
/home/amir/boost_1_69_0/boost/hana/any.hpp
/home/amir/boost_1_69_0/boost/hana/fwd/any.hpp
/home/amir/boost_1_69_0/boost/xpressive/detail/utility/any.hpp
/home/amir/boost_1_69_0/boost/type_erasure/any.hpp
/home/amir/boost_1_69_0/boost/spirit/home/support/algorithm/any.hpp
/home/amir/boost_1_69_0/boost/proto/detail/any.hpp
```
7. Выведите в консоль все файлы, где упоминается последовательность `boost::asio`.
```sh
grep -rl "boost::asio" ~/boost_1_69_0
```
grep - команда для поиска файлов
-r - ищет во всех папках, а не только в текущей аудитории
-l - вывод имен файлов
Файлов вывело очень много, поэтому, чтобы не захламлять отчет, список прикреплен не будет
8. Скомпилируем *boost*.
```sh
$ cd ~/boost_1_69_0
$ ./bootstrap.sh
$ ./b2
```
Компиляция шла около 5-7 минут
9. Переносим все скомпилированные на предыдущем шаге статические библиотеки в директорию `~/boost-libs`.
```sh
$ mkdir -p ~/boost-libs
$ mv ~/boost_1_69_0/stage/lib/* ~/boost-libs/
```
10. Подсчитайте сколько занимает дискового пространства каждый файл в этой директории.
```sh
$ cd ~/boost-libs
$ ls -lh
```
Всего файлы занимают 38Мб. Список файлов также очень длинный
11. Найдем *топ10* самых "тяжёлых".
```sh
$ ls -S | head -10
```
```sh
libboost_wave.a
libboost_regex.a
libboost_math_tr1.a
libboost_math_tr1l.a
libboost_math_tr1f.a
libboost_test_exec_monitor.a
libboost_unit_test_framework.a
libboost_locale.a
libboost_program_options.a
libboost_serialization.a
```
