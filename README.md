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

<details><summary>Установка</summary>--2026-02-17 15:45:34--  https://sourceforge.net/projects/boost/files/boost/1.69.0/boost_1_69_0.tar.gz
Resolving sourceforge.net (sourceforge.net)... 104.18.13.149, 104.18.12.149, 2606:4700::6812:c95, ...
Connecting to sourceforge.net (sourceforge.net)|104.18.13.149|:443... connected.
HTTP request sent, awaiting response... 301 Moved Permanently
Location: https://sourceforge.net/projects/boost/files/boost/1.69.0/boost_1_69_0.tar.gz/ [following]
--2026-02-17 15:45:34--  https://sourceforge.net/projects/boost/files/boost/1.69.0/boost_1_69_0.tar.gz/
Reusing existing connection to sourceforge.net:443.
HTTP request sent, awaiting response... 301 Moved Permanently
Location: https://sourceforge.net/projects/boost/files/boost/1.69.0/boost_1_69_0.tar.gz/download [following]
--2026-02-17 15:45:35--  https://sourceforge.net/projects/boost/files/boost/1.69.0/boost_1_69_0.tar.gz/download
Reusing existing connection to sourceforge.net:443.
HTTP request sent, awaiting response... 302 Found
Location: https://downloads.sourceforge.net/project/boost/boost/1.69.0/boost_1_69_0.tar.gz?ts=gAAAAABplG6Up1bGqQFcCz_dNdWXyZwKqXxHBHctYdPo6Q9jBr_q7JYK1J-EXxgvMkXNUF_C9Qcn5VkbKPUklCC6fM8af4YDzA%3D%3D&use_mirror=sf-eu-introserv-1&r= [following]
--2026-02-17 15:45:35--  https://downloads.sourceforge.net/project/boost/boost/1.69.0/boost_1_69_0.tar.gz?ts=gAAAAABplG6Up1bGqQFcCz_dNdWXyZwKqXxHBHctYdPo6Q9jBr_q7JYK1J-EXxgvMkXNUF_C9Qcn5VkbKPUklCC6fM8af4YDzA%3D%3D&use_mirror=sf-eu-introserv-1&r=
Resolving downloads.sourceforge.net (downloads.sourceforge.net)... 104.18.12.149, 104.18.13.149, 2606:4700::6812:c95, ...
Connecting to downloads.sourceforge.net (downloads.sourceforge.net)|104.18.12.149|:443... connected.
HTTP request sent, awaiting response... 302 Found
Location: https://sf-eu-introserv-1.dl.sourceforge.net/project/boost/boost/1.69.0/boost_1_69_0.tar.gz?viasf=1 [following]
--2026-02-17 15:45:35--  https://sf-eu-introserv-1.dl.sourceforge.net/project/boost/boost/1.69.0/boost_1_69_0.tar.gz?viasf=1
Resolving sf-eu-introserv-1.dl.sourceforge.net (sf-eu-introserv-1.dl.sourceforge.net)... 141.95.66.71
Connecting to sf-eu-introserv-1.dl.sourceforge.net (sf-eu-introserv-1.dl.sourceforge.net)|141.95.66.71|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 111710205 (107M) [application/x-gzip]
Saving to: ‘boost_1_69_0.tar.gz’

boost_1_69_0.tar.gz 100%[===================>] 106.53M   305KB/s    in 7m 5s   

2026-02-17 15:52:40 (257 KB/s) - ‘boost_1_69_0.tar.gz’ saved [111710205/111710205]</details>

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
Программа выдала значение 62053 файла

5. 1)Подсчитываем количество заголовочных файлов
```sh
$ find ~/boost_1_69_0 -type f \( -name "*.h" -o -name "*.hpp" -o -name "*.hxx" \) | wc -l
-name "*.h" — имя файла заканчивается на .h.
-o — логическое ИЛИ 
-name "*.hpp" — имя файла заканчивается на .hpp.
-name "*.hxx" — имя файла заканчивается на .hxx.
```
Программа выдала значение 15208 файлов

2)Файлов с расширением `.cpp`
```sh
$ find ~/boost_1_69_0 -type f -name "*.cpp" | wc -l
```
Программа выдала значение 13789 файлов

3)Сколько остальных файлов (не заголовочных и не `.cpp`).
```sh
$ find ~/boost_1_69_0 -type f ! \( -name "*.h" -o -name "*.hpp" -o -name "*.hxx" -o -name "*.cpp" \) | wc -l
```
То есть прописываем ту же команду, что в пункте 1, то перед скобками ставим !, что означает НЕ

Программа выдала значение 33056 файлов

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

<details><summary>Список файлов</summary>/home/amir/boost_1_69_0/boost/log/sinks/syslog_backend.hpp
/home/amir/boost_1_69_0/boost/process/async.hpp
/home/amir/boost_1_69_0/boost/process/detail/windows/async_out.hpp
/home/amir/boost_1_69_0/boost/process/detail/windows/async_in.hpp
/home/amir/boost_1_69_0/boost/process/detail/windows/async_pipe.hpp
/home/amir/boost_1_69_0/boost/process/detail/windows/io_context_ref.hpp
/home/amir/boost_1_69_0/boost/process/detail/async_handler.hpp
/home/amir/boost_1_69_0/boost/process/detail/traits/async.hpp
/home/amir/boost_1_69_0/boost/process/detail/posix/sigchld_service.hpp
/home/amir/boost_1_69_0/boost/process/detail/posix/async_out.hpp
/home/amir/boost_1_69_0/boost/process/detail/posix/async_in.hpp
/home/amir/boost_1_69_0/boost/process/detail/posix/async_pipe.hpp
/home/amir/boost_1_69_0/boost/process/detail/posix/io_context_ref.hpp
/home/amir/boost_1_69_0/boost/process/async_system.hpp
/home/amir/boost_1_69_0/boost/process/io.hpp
/home/amir/boost_1_69_0/boost/process/spawn.hpp
/home/amir/boost_1_69_0/boost/process/system.hpp
/home/amir/boost_1_69_0/boost/process/async_pipe.hpp
/home/amir/boost_1_69_0/boost/beast/core/buffers_prefix.hpp
/home/amir/boost_1_69_0/boost/beast/core/detail/bind_handler.hpp
/home/amir/boost_1_69_0/boost/beast/core/detail/buffers_ref.hpp
/home/amir/boost_1_69_0/boost/beast/core/detail/type_traits.hpp
/home/amir/boost_1_69_0/boost/beast/core/buffers_cat.hpp
/home/amir/boost_1_69_0/boost/beast/core/buffers_adapter.hpp
/home/amir/boost_1_69_0/boost/beast/core/buffers_suffix.hpp
/home/amir/boost_1_69_0/boost/beast/core/buffered_read_stream.hpp
/home/amir/boost_1_69_0/boost/beast/core/ostream.hpp
/home/amir/boost_1_69_0/boost/beast/core/flat_static_buffer.hpp
/home/amir/boost_1_69_0/boost/beast/core/flat_buffer.hpp
/home/amir/boost_1_69_0/boost/beast/core/buffers_to_string.hpp
/home/amir/boost_1_69_0/boost/beast/core/static_buffer.hpp
/home/amir/boost_1_69_0/boost/beast/core/multi_buffer.hpp
/home/amir/boost_1_69_0/boost/beast/core/bind_handler.hpp
/home/amir/boost_1_69_0/boost/beast/core/impl/read_size.ipp
/home/amir/boost_1_69_0/boost/beast/core/impl/handler_ptr.ipp
/home/amir/boost_1_69_0/boost/beast/core/impl/buffers_suffix.ipp
/home/amir/boost_1_69_0/boost/beast/core/impl/buffers_prefix.ipp
/home/amir/boost_1_69_0/boost/beast/core/impl/buffered_read_stream.ipp
/home/amir/boost_1_69_0/boost/beast/core/impl/flat_buffer.ipp
/home/amir/boost_1_69_0/boost/beast/core/impl/static_buffer.ipp
/home/amir/boost_1_69_0/boost/beast/core/impl/buffers_adapter.ipp
/home/amir/boost_1_69_0/boost/beast/core/impl/multi_buffer.ipp
/home/amir/boost_1_69_0/boost/beast/core/impl/flat_static_buffer.ipp
/home/amir/boost_1_69_0/boost/beast/core/impl/buffers_cat.ipp
/home/amir/boost_1_69_0/boost/beast/core/type_traits.hpp
/home/amir/boost_1_69_0/boost/beast/websocket/detail/frame.hpp
/home/amir/boost_1_69_0/boost/beast/websocket/detail/stream_base.hpp
/home/amir/boost_1_69_0/boost/beast/websocket/detail/utf8_checker.hpp
/home/amir/boost_1_69_0/boost/beast/websocket/detail/mask.hpp
/home/amir/boost_1_69_0/boost/beast/websocket/detail/pausation.hpp
/home/amir/boost_1_69_0/boost/beast/websocket/role.hpp
/home/amir/boost_1_69_0/boost/beast/websocket/ssl.hpp
/home/amir/boost_1_69_0/boost/beast/websocket/stream.hpp
/home/amir/boost_1_69_0/boost/beast/websocket/teardown.hpp
/home/amir/boost_1_69_0/boost/beast/websocket/rfc6455.hpp
/home/amir/boost_1_69_0/boost/beast/websocket/impl/ping.ipp
/home/amir/boost_1_69_0/boost/beast/websocket/impl/accept.ipp
/home/amir/boost_1_69_0/boost/beast/websocket/impl/stream.ipp
/home/amir/boost_1_69_0/boost/beast/websocket/impl/ssl.ipp
/home/amir/boost_1_69_0/boost/beast/websocket/impl/close.ipp
/home/amir/boost_1_69_0/boost/beast/websocket/impl/handshake.ipp
/home/amir/boost_1_69_0/boost/beast/websocket/impl/write.ipp
/home/amir/boost_1_69_0/boost/beast/websocket/impl/teardown.ipp
/home/amir/boost_1_69_0/boost/beast/websocket/impl/read.ipp
/home/amir/boost_1_69_0/boost/beast/http/read.hpp
/home/amir/boost_1_69_0/boost/beast/http/serializer.hpp
/home/amir/boost_1_69_0/boost/beast/http/vector_body.hpp
/home/amir/boost_1_69_0/boost/beast/http/chunk_encode.hpp
/home/amir/boost_1_69_0/boost/beast/http/detail/chunk_encode.hpp
/home/amir/boost_1_69_0/boost/beast/http/write.hpp
/home/amir/boost_1_69_0/boost/beast/http/basic_parser.hpp
/home/amir/boost_1_69_0/boost/beast/http/empty_body.hpp
/home/amir/boost_1_69_0/boost/beast/http/string_body.hpp
/home/amir/boost_1_69_0/boost/beast/http/span_body.hpp
/home/amir/boost_1_69_0/boost/beast/http/basic_dynamic_body.hpp
/home/amir/boost_1_69_0/boost/beast/http/fields.hpp
/home/amir/boost_1_69_0/boost/beast/http/impl/file_body_win32.ipp
/home/amir/boost_1_69_0/boost/beast/http/impl/basic_parser.ipp
/home/amir/boost_1_69_0/boost/beast/http/impl/chunk_encode.ipp
/home/amir/boost_1_69_0/boost/beast/http/impl/write.ipp
/home/amir/boost_1_69_0/boost/beast/http/impl/fields.ipp
/home/amir/boost_1_69_0/boost/beast/http/impl/serializer.ipp
/home/amir/boost_1_69_0/boost/beast/http/impl/read.ipp
/home/amir/boost_1_69_0/boost/beast/http/parser.hpp
/home/amir/boost_1_69_0/boost/beast/http/basic_file_body.hpp
/home/amir/boost_1_69_0/boost/beast/http/buffer_body.hpp
/home/amir/boost_1_69_0/boost/beast/http/error.hpp
/home/amir/boost_1_69_0/boost/beast/http/type_traits.hpp
/home/amir/boost_1_69_0/boost/beast/experimental/core/detail/flat_stream.hpp
/home/amir/boost_1_69_0/boost/beast/experimental/core/detail/timeout_service.hpp
/home/amir/boost_1_69_0/boost/beast/experimental/core/detail/service_base.hpp
/home/amir/boost_1_69_0/boost/beast/experimental/core/detail/impl/timeout_service.ipp
/home/amir/boost_1_69_0/boost/beast/experimental/core/timeout_socket.hpp
/home/amir/boost_1_69_0/boost/beast/experimental/core/ssl_stream.hpp
/home/amir/boost_1_69_0/boost/beast/experimental/core/flat_stream.hpp
/home/amir/boost_1_69_0/boost/beast/experimental/core/timeout_service.hpp
/home/amir/boost_1_69_0/boost/beast/experimental/core/impl/timeout_service.ipp
/home/amir/boost_1_69_0/boost/beast/experimental/core/impl/flat_stream.ipp
/home/amir/boost_1_69_0/boost/beast/experimental/core/impl/timeout_socket.hpp
/home/amir/boost_1_69_0/boost/beast/experimental/test/stream.hpp
/home/amir/boost_1_69_0/boost/beast/experimental/test/impl/stream.ipp
/home/amir/boost_1_69_0/boost/beast/experimental/http/icy_stream.hpp
/home/amir/boost_1_69_0/boost/beast/experimental/http/impl/icy_stream.ipp
/home/amir/boost_1_69_0/boost/asio/signal_set_service.hpp
/home/amir/boost_1_69_0/boost/asio/read.hpp
/home/amir/boost_1_69_0/boost/asio/basic_io_object.hpp
/home/amir/boost_1_69_0/boost/asio/buffer.hpp
/home/amir/boost_1_69_0/boost/asio/is_executor.hpp
/home/amir/boost_1_69_0/boost/asio/basic_deadline_timer.hpp
/home/amir/boost_1_69_0/boost/asio/datagram_socket_service.hpp
/home/amir/boost_1_69_0/boost/asio/basic_socket_iostream.hpp
/home/amir/boost_1_69_0/boost/asio/basic_serial_port.hpp
/home/amir/boost_1_69_0/boost/asio/async_result.hpp
/home/amir/boost_1_69_0/boost/asio/ts/netfwd.hpp
/home/amir/boost_1_69_0/boost/asio/basic_stream_socket.hpp
/home/amir/boost_1_69_0/boost/asio/detail/signal_set_service.hpp
/home/amir/boost_1_69_0/boost/asio/detail/handler_tracking.hpp
/home/amir/boost_1_69_0/boost/asio/detail/win_iocp_socket_recvmsg_op.hpp
/home/amir/boost_1_69_0/boost/asio/detail/std_mutex.hpp
/home/amir/boost_1_69_0/boost/asio/detail/resolve_endpoint_op.hpp
/home/amir/boost_1_69_0/boost/asio/detail/win_iocp_socket_send_op.hpp
/home/amir/boost_1_69_0/boost/asio/detail/completion_handler.hpp
/home/amir/boost_1_69_0/boost/asio/detail/descriptor_write_op.hpp
/home/amir/boost_1_69_0/boost/asio/detail/winrt_utils.hpp
/home/amir/boost_1_69_0/boost/asio/detail/winapp_thread.hpp
/home/amir/boost_1_69_0/boost/asio/detail/string_view.hpp
/home/amir/boost_1_69_0/boost/asio/detail/null_mutex.hpp
/home/amir/boost_1_69_0/boost/asio/detail/reactor_op_queue.hpp
/home/amir/boost_1_69_0/boost/asio/detail/strand_service.hpp
/home/amir/boost_1_69_0/boost/asio/detail/winrt_socket_recv_op.hpp
/home/amir/boost_1_69_0/boost/asio/detail/win_iocp_socket_recv_op.hpp
/home/amir/boost_1_69_0/boost/asio/detail/thread_group.hpp
/home/amir/boost_1_69_0/boost/asio/detail/resolver_service_base.hpp
/home/amir/boost_1_69_0/boost/asio/detail/win_iocp_socket_service.hpp
/home/amir/boost_1_69_0/boost/asio/detail/select_reactor.hpp
/home/amir/boost_1_69_0/boost/asio/detail/resolver_service.hpp
/home/amir/boost_1_69_0/boost/asio/detail/winrt_resolver_service.hpp
/home/amir/boost_1_69_0/boost/asio/detail/null_thread.hpp
/home/amir/boost_1_69_0/boost/asio/detail/std_static_mutex.hpp
/home/amir/boost_1_69_0/boost/asio/detail/win_iocp_handle_write_op.hpp
/home/amir/boost_1_69_0/boost/asio/detail/reactive_socket_connect_op.hpp
/home/amir/boost_1_69_0/boost/asio/detail/is_buffer_sequence.hpp
/home/amir/boost_1_69_0/boost/asio/detail/win_iocp_overlapped_ptr.hpp
/home/amir/boost_1_69_0/boost/asio/detail/reactive_socket_recvfrom_op.hpp
/home/amir/boost_1_69_0/boost/asio/detail/socket_option.hpp
/home/amir/boost_1_69_0/boost/asio/detail/timer_queue.hpp
/home/amir/boost_1_69_0/boost/asio/detail/handler_alloc_helpers.hpp
/home/amir/boost_1_69_0/boost/asio/detail/epoll_reactor.hpp
/home/amir/boost_1_69_0/boost/asio/detail/winrt_socket_send_op.hpp
/home/amir/boost_1_69_0/boost/asio/detail/win_iocp_io_context.hpp
/home/amir/boost_1_69_0/boost/asio/detail/reactive_descriptor_service.hpp
/home/amir/boost_1_69_0/boost/asio/detail/win_iocp_socket_recvfrom_op.hpp
/home/amir/boost_1_69_0/boost/asio/detail/win_iocp_overlapped_op.hpp
/home/amir/boost_1_69_0/boost/asio/detail/win_iocp_serial_port_service.hpp
/home/amir/boost_1_69_0/boost/asio/detail/reactive_socket_sendto_op.hpp
/home/amir/boost_1_69_0/boost/asio/detail/reactive_socket_recvmsg_op.hpp
/home/amir/boost_1_69_0/boost/asio/detail/win_static_mutex.hpp
/home/amir/boost_1_69_0/boost/asio/detail/win_iocp_wait_op.hpp
/home/amir/boost_1_69_0/boost/asio/detail/winrt_ssocket_service_base.hpp
/home/amir/boost_1_69_0/boost/asio/detail/null_static_mutex.hpp
/home/amir/boost_1_69_0/boost/asio/detail/scheduler.hpp
/home/amir/boost_1_69_0/boost/asio/detail/resolve_query_op.hpp
/home/amir/boost_1_69_0/boost/asio/detail/conditionally_enabled_mutex.hpp
/home/amir/boost_1_69_0/boost/asio/detail/kqueue_reactor.hpp
/home/amir/boost_1_69_0/boost/asio/detail/wince_thread.hpp
/home/amir/boost_1_69_0/boost/asio/detail/signal_handler.hpp
/home/amir/boost_1_69_0/boost/asio/detail/wait_handler.hpp
/home/amir/boost_1_69_0/boost/asio/detail/descriptor_ops.hpp
/home/amir/boost_1_69_0/boost/asio/detail/posix_mutex.hpp
/home/amir/boost_1_69_0/boost/asio/detail/reactive_serial_port_service.hpp
/home/amir/boost_1_69_0/boost/asio/detail/winrt_resolve_op.hpp
/home/amir/boost_1_69_0/boost/asio/detail/win_mutex.hpp
/home/amir/boost_1_69_0/boost/asio/detail/win_iocp_null_buffers_op.hpp
/home/amir/boost_1_69_0/boost/asio/detail/deadline_timer_service.hpp
/home/amir/boost_1_69_0/boost/asio/detail/dev_poll_reactor.hpp
/home/amir/boost_1_69_0/boost/asio/detail/win_object_handle_service.hpp
/home/amir/boost_1_69_0/boost/asio/detail/handler_invoke_helpers.hpp
/home/amir/boost_1_69_0/boost/asio/detail/null_socket_service.hpp
/home/amir/boost_1_69_0/boost/asio/detail/handler_cont_helpers.hpp
/home/amir/boost_1_69_0/boost/asio/detail/buffer_sequence_adapter.hpp
/home/amir/boost_1_69_0/boost/asio/detail/win_iocp_socket_service_base.hpp
/home/amir/boost_1_69_0/boost/asio/detail/win_iocp_socket_connect_op.hpp
/home/amir/boost_1_69_0/boost/asio/detail/reactive_socket_recv_op.hpp
/home/amir/boost_1_69_0/boost/asio/detail/winrt_ssocket_service.hpp
/home/amir/boost_1_69_0/boost/asio/detail/win_iocp_handle_service.hpp
/home/amir/boost_1_69_0/boost/asio/detail/win_iocp_socket_accept_op.hpp
/home/amir/boost_1_69_0/boost/asio/detail/reactive_socket_service.hpp
/home/amir/boost_1_69_0/boost/asio/detail/buffered_stream_storage.hpp
/home/amir/boost_1_69_0/boost/asio/detail/service_registry.hpp
/home/amir/boost_1_69_0/boost/asio/detail/posix_static_mutex.hpp
/home/amir/boost_1_69_0/boost/asio/detail/consuming_buffers.hpp
/home/amir/boost_1_69_0/boost/asio/detail/reactive_null_buffers_op.hpp
/home/amir/boost_1_69_0/boost/asio/detail/winrt_timer_scheduler.hpp
/home/amir/boost_1_69_0/boost/asio/detail/conditionally_enabled_event.hpp
/home/amir/boost_1_69_0/boost/asio/detail/noncopyable.hpp
/home/amir/boost_1_69_0/boost/asio/detail/null_reactor.hpp
/home/amir/boost_1_69_0/boost/asio/detail/winrt_async_manager.hpp
/home/amir/boost_1_69_0/boost/asio/detail/reactive_socket_accept_op.hpp
/home/amir/boost_1_69_0/boost/asio/detail/reactive_socket_service_base.hpp
/home/amir/boost_1_69_0/boost/asio/detail/descriptor_read_op.hpp
/home/amir/boost_1_69_0/boost/asio/detail/win_iocp_handle_read_op.hpp
/home/amir/boost_1_69_0/boost/asio/detail/impl/kqueue_reactor.ipp
/home/amir/boost_1_69_0/boost/asio/detail/impl/socket_select_interrupter.ipp
/home/amir/boost_1_69_0/boost/asio/detail/impl/scheduler.ipp
/home/amir/boost_1_69_0/boost/asio/detail/impl/pipe_select_interrupter.ipp
/home/amir/boost_1_69_0/boost/asio/detail/impl/posix_thread.ipp
/home/amir/boost_1_69_0/boost/asio/detail/impl/service_registry.ipp
/home/amir/boost_1_69_0/boost/asio/detail/impl/epoll_reactor.ipp
/home/amir/boost_1_69_0/boost/asio/detail/impl/win_static_mutex.ipp
/home/amir/boost_1_69_0/boost/asio/detail/impl/win_iocp_socket_service_base.ipp
/home/amir/boost_1_69_0/boost/asio/detail/impl/strand_service.hpp
/home/amir/boost_1_69_0/boost/asio/detail/impl/posix_tss_ptr.ipp
/home/amir/boost_1_69_0/boost/asio/detail/impl/select_reactor.hpp
/home/amir/boost_1_69_0/boost/asio/detail/impl/reactive_descriptor_service.ipp
/home/amir/boost_1_69_0/boost/asio/detail/impl/posix_event.ipp
/home/amir/boost_1_69_0/boost/asio/detail/impl/buffer_sequence_adapter.ipp
/home/amir/boost_1_69_0/boost/asio/detail/impl/posix_mutex.ipp
/home/amir/boost_1_69_0/boost/asio/detail/impl/win_iocp_io_context.hpp
/home/amir/boost_1_69_0/boost/asio/detail/impl/descriptor_ops.ipp
/home/amir/boost_1_69_0/boost/asio/detail/impl/socket_ops.ipp
/home/amir/boost_1_69_0/boost/asio/detail/impl/handler_tracking.ipp
/home/amir/boost_1_69_0/boost/asio/detail/impl/win_thread.ipp
/home/amir/boost_1_69_0/boost/asio/detail/impl/strand_executor_service.ipp
/home/amir/boost_1_69_0/boost/asio/detail/impl/resolver_service_base.ipp
/home/amir/boost_1_69_0/boost/asio/detail/impl/reactive_serial_port_service.ipp
/home/amir/boost_1_69_0/boost/asio/detail/impl/signal_set_service.ipp
/home/amir/boost_1_69_0/boost/asio/detail/impl/reactive_socket_service_base.ipp
/home/amir/boost_1_69_0/boost/asio/detail/impl/win_iocp_io_context.ipp
/home/amir/boost_1_69_0/boost/asio/detail/impl/win_iocp_serial_port_service.ipp
/home/amir/boost_1_69_0/boost/asio/detail/impl/win_event.ipp
/home/amir/boost_1_69_0/boost/asio/detail/impl/select_reactor.ipp
/home/amir/boost_1_69_0/boost/asio/detail/impl/dev_poll_reactor.ipp
/home/amir/boost_1_69_0/boost/asio/detail/impl/eventfd_select_interrupter.ipp
/home/amir/boost_1_69_0/boost/asio/detail/impl/strand_service.ipp
/home/amir/boost_1_69_0/boost/asio/detail/impl/win_mutex.ipp
/home/amir/boost_1_69_0/boost/asio/detail/impl/dev_poll_reactor.hpp
/home/amir/boost_1_69_0/boost/asio/detail/impl/winrt_ssocket_service_base.ipp
/home/amir/boost_1_69_0/boost/asio/detail/impl/win_object_handle_service.ipp
/home/amir/boost_1_69_0/boost/asio/detail/impl/throw_error.ipp
/home/amir/boost_1_69_0/boost/asio/detail/impl/winrt_timer_scheduler.hpp
/home/amir/boost_1_69_0/boost/asio/detail/impl/win_iocp_handle_service.ipp
/home/amir/boost_1_69_0/boost/asio/detail/impl/win_tss_ptr.ipp
/home/amir/boost_1_69_0/boost/asio/detail/impl/winsock_init.ipp
/home/amir/boost_1_69_0/boost/asio/detail/impl/winrt_timer_scheduler.ipp
/home/amir/boost_1_69_0/boost/asio/detail/winsock_init.hpp
/home/amir/boost_1_69_0/boost/asio/detail/reactive_socket_send_op.hpp
/home/amir/boost_1_69_0/boost/asio/detail/handler_type_requirements.hpp
/home/amir/boost_1_69_0/boost/asio/detail/reactive_wait_op.hpp
/home/amir/boost_1_69_0/boost/asio/detail/winrt_socket_connect_op.hpp
/home/amir/boost_1_69_0/boost/asio/handler_invoke_hook.hpp
/home/amir/boost_1_69_0/boost/asio/placeholders.hpp
/home/amir/boost_1_69_0/boost/asio/basic_waitable_timer.hpp
/home/amir/boost_1_69_0/boost/asio/thread_pool.hpp
/home/amir/boost_1_69_0/boost/asio/io_context.hpp
/home/amir/boost_1_69_0/boost/asio/write.hpp
/home/amir/boost_1_69_0/boost/asio/basic_datagram_socket.hpp
/home/amir/boost_1_69_0/boost/asio/basic_raw_socket.hpp
/home/amir/boost_1_69_0/boost/asio/socket_acceptor_service.hpp
/home/amir/boost_1_69_0/boost/asio/local/datagram_protocol.hpp
/home/amir/boost_1_69_0/boost/asio/local/detail/endpoint.hpp
/home/amir/boost_1_69_0/boost/asio/local/detail/impl/endpoint.ipp
/home/amir/boost_1_69_0/boost/asio/local/basic_endpoint.hpp
/home/amir/boost_1_69_0/boost/asio/local/connect_pair.hpp
/home/amir/boost_1_69_0/boost/asio/local/stream_protocol.hpp
/home/amir/boost_1_69_0/boost/asio/serial_port.hpp
/home/amir/boost_1_69_0/boost/asio/serial_port_service.hpp
/home/amir/boost_1_69_0/boost/asio/buffers_iterator.hpp
/home/amir/boost_1_69_0/boost/asio/completion_condition.hpp
/home/amir/boost_1_69_0/boost/asio/generic/datagram_protocol.hpp
/home/amir/boost_1_69_0/boost/asio/generic/raw_protocol.hpp
/home/amir/boost_1_69_0/boost/asio/generic/detail/endpoint.hpp
/home/amir/boost_1_69_0/boost/asio/generic/detail/impl/endpoint.ipp
/home/amir/boost_1_69_0/boost/asio/generic/seq_packet_protocol.hpp
/home/amir/boost_1_69_0/boost/asio/generic/basic_endpoint.hpp
/home/amir/boost_1_69_0/boost/asio/generic/stream_protocol.hpp
/home/amir/boost_1_69_0/boost/asio/spawn.hpp
/home/amir/boost_1_69_0/boost/asio/basic_socket_streambuf.hpp
/home/amir/boost_1_69_0/boost/asio/uses_executor.hpp
/home/amir/boost_1_69_0/boost/asio/buffered_read_stream.hpp
/home/amir/boost_1_69_0/boost/asio/windows/object_handle.hpp
/home/amir/boost_1_69_0/boost/asio/windows/random_access_handle.hpp
/home/amir/boost_1_69_0/boost/asio/windows/object_handle_service.hpp
/home/amir/boost_1_69_0/boost/asio/windows/overlapped_ptr.hpp
/home/amir/boost_1_69_0/boost/asio/windows/basic_stream_handle.hpp
/home/amir/boost_1_69_0/boost/asio/windows/basic_handle.hpp
/home/amir/boost_1_69_0/boost/asio/windows/stream_handle.hpp
/home/amir/boost_1_69_0/boost/asio/windows/stream_handle_service.hpp
/home/amir/boost_1_69_0/boost/asio/windows/overlapped_handle.hpp
/home/amir/boost_1_69_0/boost/asio/windows/random_access_handle_service.hpp
/home/amir/boost_1_69_0/boost/asio/windows/basic_random_access_handle.hpp
/home/amir/boost_1_69_0/boost/asio/windows/basic_object_handle.hpp
/home/amir/boost_1_69_0/boost/asio/basic_signal_set.hpp
/home/amir/boost_1_69_0/boost/asio/write_at.hpp
/home/amir/boost_1_69_0/boost/asio/signal_set.hpp
/home/amir/boost_1_69_0/boost/asio/ssl/context_base.hpp
/home/amir/boost_1_69_0/boost/asio/ssl/detail/openssl_init.hpp
/home/amir/boost_1_69_0/boost/asio/ssl/detail/stream_core.hpp
/home/amir/boost_1_69_0/boost/asio/ssl/detail/buffered_handshake_op.hpp
/home/amir/boost_1_69_0/boost/asio/ssl/detail/io.hpp
/home/amir/boost_1_69_0/boost/asio/ssl/detail/engine.hpp
/home/amir/boost_1_69_0/boost/asio/ssl/detail/write_op.hpp
/home/amir/boost_1_69_0/boost/asio/ssl/detail/read_op.hpp
/home/amir/boost_1_69_0/boost/asio/ssl/detail/impl/openssl_init.ipp
/home/amir/boost_1_69_0/boost/asio/ssl/detail/impl/engine.ipp
/home/amir/boost_1_69_0/boost/asio/ssl/context.hpp
/home/amir/boost_1_69_0/boost/asio/ssl/stream_base.hpp
/home/amir/boost_1_69_0/boost/asio/ssl/stream.hpp
/home/amir/boost_1_69_0/boost/asio/ssl/rfc2818_verification.hpp
/home/amir/boost_1_69_0/boost/asio/ssl/impl/error.ipp
/home/amir/boost_1_69_0/boost/asio/ssl/impl/context.hpp
/home/amir/boost_1_69_0/boost/asio/ssl/impl/context.ipp
/home/amir/boost_1_69_0/boost/asio/ssl/error.hpp
/home/amir/boost_1_69_0/boost/asio/basic_socket_acceptor.hpp
/home/amir/boost_1_69_0/boost/asio/experimental/detached.hpp
/home/amir/boost_1_69_0/boost/asio/experimental/impl/detached.hpp
/home/amir/boost_1_69_0/boost/asio/experimental/impl/co_spawn.hpp
/home/amir/boost_1_69_0/boost/asio/buffered_stream.hpp
/home/amir/boost_1_69_0/boost/asio/basic_socket.hpp
/home/amir/boost_1_69_0/boost/asio/use_future.hpp
/home/amir/boost_1_69_0/boost/asio/socket_base.hpp
/home/amir/boost_1_69_0/boost/asio/basic_seq_packet_socket.hpp
/home/amir/boost_1_69_0/boost/asio/ip/basic_resolver_results.hpp
/home/amir/boost_1_69_0/boost/asio/ip/icmp.hpp
/home/amir/boost_1_69_0/boost/asio/ip/address_v4.hpp
/home/amir/boost_1_69_0/boost/asio/ip/detail/socket_option.hpp
/home/amir/boost_1_69_0/boost/asio/ip/detail/endpoint.hpp
/home/amir/boost_1_69_0/boost/asio/ip/detail/impl/endpoint.ipp
/home/amir/boost_1_69_0/boost/asio/ip/unicast.hpp
/home/amir/boost_1_69_0/boost/asio/ip/resolver_service.hpp
/home/amir/boost_1_69_0/boost/asio/ip/tcp.hpp
/home/amir/boost_1_69_0/boost/asio/ip/basic_resolver.hpp
/home/amir/boost_1_69_0/boost/asio/ip/udp.hpp
/home/amir/boost_1_69_0/boost/asio/ip/basic_endpoint.hpp
/home/amir/boost_1_69_0/boost/asio/ip/v6_only.hpp
/home/amir/boost_1_69_0/boost/asio/ip/multicast.hpp
/home/amir/boost_1_69_0/boost/asio/ip/basic_resolver_query.hpp
/home/amir/boost_1_69_0/boost/asio/ip/network_v4.hpp
/home/amir/boost_1_69_0/boost/asio/ip/address.hpp
/home/amir/boost_1_69_0/boost/asio/ip/basic_resolver_entry.hpp
/home/amir/boost_1_69_0/boost/asio/ip/basic_resolver_iterator.hpp
/home/amir/boost_1_69_0/boost/asio/ip/impl/address_v6.ipp
/home/amir/boost_1_69_0/boost/asio/ip/impl/address_v4.hpp
/home/amir/boost_1_69_0/boost/asio/ip/impl/network_v4.ipp
/home/amir/boost_1_69_0/boost/asio/ip/impl/network_v6.ipp
/home/amir/boost_1_69_0/boost/asio/ip/impl/address_v4.ipp
/home/amir/boost_1_69_0/boost/asio/ip/impl/basic_endpoint.hpp
/home/amir/boost_1_69_0/boost/asio/ip/impl/network_v4.hpp
/home/amir/boost_1_69_0/boost/asio/ip/impl/address.hpp
/home/amir/boost_1_69_0/boost/asio/ip/impl/address.ipp
/home/amir/boost_1_69_0/boost/asio/ip/impl/host_name.ipp
/home/amir/boost_1_69_0/boost/asio/ip/impl/address_v6.hpp
/home/amir/boost_1_69_0/boost/asio/ip/impl/network_v6.hpp
/home/amir/boost_1_69_0/boost/asio/ip/address_v6.hpp
/home/amir/boost_1_69_0/boost/asio/ip/network_v6.hpp
/home/amir/boost_1_69_0/boost/asio/deadline_timer_service.hpp
/home/amir/boost_1_69_0/boost/asio/stream_socket_service.hpp
/home/amir/boost_1_69_0/boost/asio/io_context_strand.hpp
/home/amir/boost_1_69_0/boost/asio/raw_socket_service.hpp
/home/amir/boost_1_69_0/boost/asio/read_at.hpp
/home/amir/boost_1_69_0/boost/asio/connect.hpp
/home/amir/boost_1_69_0/boost/asio/execution_context.hpp
/home/amir/boost_1_69_0/boost/asio/coroutine.hpp
/home/amir/boost_1_69_0/boost/asio/executor.hpp
/home/amir/boost_1_69_0/boost/asio/basic_streambuf.hpp
/home/amir/boost_1_69_0/boost/asio/posix/stream_descriptor_service.hpp
/home/amir/boost_1_69_0/boost/asio/posix/basic_stream_descriptor.hpp
/home/amir/boost_1_69_0/boost/asio/posix/stream_descriptor.hpp
/home/amir/boost_1_69_0/boost/asio/posix/descriptor_base.hpp
/home/amir/boost_1_69_0/boost/asio/posix/descriptor.hpp
/home/amir/boost_1_69_0/boost/asio/posix/basic_descriptor.hpp
/home/amir/boost_1_69_0/boost/asio/seq_packet_socket_service.hpp
/home/amir/boost_1_69_0/boost/asio/read_until.hpp
/home/amir/boost_1_69_0/boost/asio/waitable_timer_service.hpp
/home/amir/boost_1_69_0/boost/asio/impl/read.hpp
/home/amir/boost_1_69_0/boost/asio/impl/io_context.hpp
/home/amir/boost_1_69_0/boost/asio/impl/write.hpp
/home/amir/boost_1_69_0/boost/asio/impl/serial_port_base.ipp
/home/amir/boost_1_69_0/boost/asio/impl/spawn.hpp
/home/amir/boost_1_69_0/boost/asio/impl/buffered_read_stream.hpp
/home/amir/boost_1_69_0/boost/asio/impl/write_at.hpp
/home/amir/boost_1_69_0/boost/asio/impl/execution_context.ipp
/home/amir/boost_1_69_0/boost/asio/impl/io_context.ipp
/home/amir/boost_1_69_0/boost/asio/impl/read_at.hpp
/home/amir/boost_1_69_0/boost/asio/impl/connect.hpp
/home/amir/boost_1_69_0/boost/asio/impl/read_until.hpp
/home/amir/boost_1_69_0/boost/asio/impl/buffered_write_stream.hpp
/home/amir/boost_1_69_0/boost/asio/buffered_write_stream.hpp
/home/amir/boost_1_69_0/boost/asio/error.hpp
/home/amir/boost_1_69_0/doc/html/boost_asio/examples/cpp03_examples.html
/home/amir/boost_1_69_0/doc/html/boost_asio/examples/cpp11_examples.html
/home/amir/boost_1_69_0/doc/html/boost_asio/tutorial/tuttimer3.html
/home/amir/boost_1_69_0/doc/html/boost_asio/tutorial/tutdaytime5/src.html
/home/amir/boost_1_69_0/doc/html/boost_asio/tutorial/tutdaytime5.html
/home/amir/boost_1_69_0/doc/html/boost_asio/tutorial/tutdaytime1/src.html
/home/amir/boost_1_69_0/doc/html/boost_asio/tutorial/tutdaytime2/src.html
/home/amir/boost_1_69_0/doc/html/boost_asio/tutorial/tutdaytime7.html
/home/amir/boost_1_69_0/doc/html/boost_asio/tutorial/tuttimer2.html
/home/amir/boost_1_69_0/doc/html/boost_asio/tutorial/tuttimer2/src.html
/home/amir/boost_1_69_0/doc/html/boost_asio/tutorial/tutdaytime4.html
/home/amir/boost_1_69_0/doc/html/boost_asio/tutorial/tuttimer4.html
/home/amir/boost_1_69_0/doc/html/boost_asio/tutorial/tutdaytime4/src.html
/home/amir/boost_1_69_0/doc/html/boost_asio/tutorial/tuttimer5/src.html
/home/amir/boost_1_69_0/doc/html/boost_asio/tutorial/tutdaytime3.html
/home/amir/boost_1_69_0/doc/html/boost_asio/tutorial/tutdaytime2.html
/home/amir/boost_1_69_0/doc/html/boost_asio/tutorial/tutdaytime6/src.html
/home/amir/boost_1_69_0/doc/html/boost_asio/tutorial/tutdaytime7/src.html
/home/amir/boost_1_69_0/doc/html/boost_asio/tutorial/tuttimer1.html
/home/amir/boost_1_69_0/doc/html/boost_asio/tutorial/tutdaytime3/src.html
/home/amir/boost_1_69_0/doc/html/boost_asio/tutorial/tuttimer3/src.html
/home/amir/boost_1_69_0/doc/html/boost_asio/tutorial/tuttimer1/src.html
/home/amir/boost_1_69_0/doc/html/boost_asio/tutorial/tutdaytime6.html
/home/amir/boost_1_69_0/doc/html/boost_asio/tutorial/tutdaytime1.html
/home/amir/boost_1_69_0/doc/html/boost_asio/tutorial/tuttimer5.html
/home/amir/boost_1_69_0/doc/html/boost_asio/tutorial/tuttimer4/src.html
/home/amir/boost_1_69_0/doc/html/boost_asio/overview/cpp2011/move_handlers.html
/home/amir/boost_1_69_0/doc/html/boost_asio/overview/cpp2011/futures.html
/home/amir/boost_1_69_0/doc/html/boost_asio/overview/core/spawn.html
/home/amir/boost_1_69_0/doc/html/boost_asio/overview/core/line_based.html
/home/amir/boost_1_69_0/doc/html/boost_asio/overview/core/strands.html
/home/amir/boost_1_69_0/doc/html/boost_asio/overview/core/coroutines_ts.html
/home/amir/boost_1_69_0/doc/html/boost_asio/overview/core/coroutine.html
/home/amir/boost_1_69_0/doc/html/boost_asio/overview/core/allocation.html
/home/amir/boost_1_69_0/doc/html/boost_asio/overview/signals.html
/home/amir/boost_1_69_0/doc/html/boost_asio/overview/networking/other_protocols.html
/home/amir/boost_1_69_0/doc/html/boost_asio/overview/networking/protocols.html
/home/amir/boost_1_69_0/doc/html/boost_asio/overview/ssl.html
/home/amir/boost_1_69_0/doc/html/boost_asio/overview/posix/stream_descriptor.html
/home/amir/boost_1_69_0/doc/html/boost_asio/overview/posix/fork.html
/home/amir/boost_1_69_0/doc/html/boost_asio/example/cpp17/coroutines_ts/refactored_echo_server.cpp
/home/amir/boost_1_69_0/doc/html/boost_asio/example/cpp17/coroutines_ts/range_based_for.cpp
/home/amir/boost_1_69_0/doc/html/boost_asio/example/cpp17/coroutines_ts/chat_server.cpp
/home/amir/boost_1_69_0/doc/html/boost_asio/example/cpp17/coroutines_ts/double_buffered_echo_server.cpp
/home/amir/boost_1_69_0/doc/html/boost_asio/example/cpp17/coroutines_ts/echo_server.cpp
/home/amir/boost_1_69_0/doc/html/boost_asio/example/cpp11/buffers/reference_counted.cpp
/home/amir/boost_1_69_0/doc/html/boost_asio/example/cpp11/fork/process_per_connection.cpp
/home/amir/boost_1_69_0/doc/html/boost_asio/example/cpp11/fork/daemon.cpp
/home/amir/boost_1_69_0/doc/html/boost_asio/example/cpp11/executors/bank_account_1.cpp
/home/amir/boost_1_69_0/doc/html/boost_asio/example/cpp11/executors/fork_join.cpp
/home/amir/boost_1_69_0/doc/html/boost_asio/example/cpp11/executors/actor.cpp
/home/amir/boost_1_69_0/doc/html/boost_asio/example/cpp11/executors/priority_scheduler.cpp
/home/amir/boost_1_69_0/doc/html/boost_asio/example/cpp11/executors/pipeline.cpp
/home/amir/boost_1_69_0/doc/html/boost_asio/example/cpp11/executors/bank_account_2.cpp
/home/amir/boost_1_69_0/doc/html/boost_asio/example/cpp11/spawn/parallel_grep.cpp
/home/amir/boost_1_69_0/doc/html/boost_asio/example/cpp11/spawn/echo_server.cpp
/home/amir/boost_1_69_0/doc/html/boost_asio/example/cpp11/futures/daytime_client.cpp
/home/amir/boost_1_69_0/doc/html/boost_asio/example/cpp11/local/stream_server.cpp
/home/amir/boost_1_69_0/doc/html/boost_asio/example/cpp11/local/stream_client.cpp
/home/amir/boost_1_69_0/doc/html/boost_asio/example/cpp11/local/iostream_client.cpp
/home/amir/boost_1_69_0/doc/html/boost_asio/example/cpp11/local/connect_pair.cpp
/home/amir/boost_1_69_0/doc/html/boost_asio/example/cpp11/timers/time_t_timer.cpp
/home/amir/boost_1_69_0/doc/html/boost_asio/example/cpp11/ssl/client.cpp
/home/amir/boost_1_69_0/doc/html/boost_asio/example/cpp11/ssl/server.cpp
/home/amir/boost_1_69_0/doc/html/boost_asio/example/cpp11/operations/composed_5.cpp
/home/amir/boost_1_69_0/doc/html/boost_asio/example/cpp11/operations/composed_3.cpp
/home/amir/boost_1_69_0/doc/html/boost_asio/example/cpp11/operations/composed_4.cpp
/home/amir/boost_1_69_0/doc/html/boost_asio/example/cpp11/operations/composed_1.cpp
/home/amir/boost_1_69_0/doc/html/boost_asio/example/cpp11/operations/composed_2.cpp
/home/amir/boost_1_69_0/doc/html/boost_asio/example/cpp11/handler_tracking/async_tcp_echo_server.cpp
/home/amir/boost_1_69_0/doc/html/boost_asio/example/cpp11/handler_tracking/custom_tracking.hpp
/home/amir/boost_1_69_0/doc/html/boost_asio/example/cpp11/socks4/sync_client.cpp
/home/amir/boost_1_69_0/doc/html/boost_asio/example/cpp11/socks4/socks4.hpp
/home/amir/boost_1_69_0/doc/html/boost_asio/example/cpp11/http/server/reply.cpp
/home/amir/boost_1_69_0/doc/html/boost_asio/example/cpp11/http/server/server.hpp
/home/amir/boost_1_69_0/doc/html/boost_asio/example/cpp11/http/server/connection.cpp
/home/amir/boost_1_69_0/doc/html/boost_asio/example/cpp11/http/server/reply.hpp
/home/amir/boost_1_69_0/doc/html/boost_asio/example/cpp11/http/server/connection.hpp
/home/amir/boost_1_69_0/doc/html/boost_asio/example/cpp11/http/server/server.cpp
/home/amir/boost_1_69_0/doc/html/boost_asio/example/cpp11/chat/chat_server.cpp
/home/amir/boost_1_69_0/doc/html/boost_asio/example/cpp11/chat/chat_client.cpp
/home/amir/boost_1_69_0/doc/html/boost_asio/example/cpp11/timeouts/server.cpp
/home/amir/boost_1_69_0/doc/html/boost_asio/example/cpp11/timeouts/blocking_tcp_client.cpp
/home/amir/boost_1_69_0/doc/html/boost_asio/example/cpp11/timeouts/async_tcp_client.cpp
/home/amir/boost_1_69_0/doc/html/boost_asio/example/cpp11/timeouts/blocking_token_tcp_client.cpp
/home/amir/boost_1_69_0/doc/html/boost_asio/example/cpp11/timeouts/blocking_udp_client.cpp
/home/amir/boost_1_69_0/doc/html/boost_asio/example/cpp11/invocation/prioritised_handlers.cpp
/home/amir/boost_1_69_0/doc/html/boost_asio/example/cpp11/echo/blocking_tcp_echo_server.cpp
/home/amir/boost_1_69_0/doc/html/boost_asio/example/cpp11/echo/blocking_tcp_echo_client.cpp
/home/amir/boost_1_69_0/doc/html/boost_asio/example/cpp11/echo/async_tcp_echo_server.cpp
/home/amir/boost_1_69_0/doc/html/boost_asio/example/cpp11/echo/blocking_udp_echo_client.cpp
/home/amir/boost_1_69_0/doc/html/boost_asio/example/cpp11/echo/async_udp_echo_server.cpp
/home/amir/boost_1_69_0/doc/html/boost_asio/example/cpp11/echo/blocking_udp_echo_server.cpp
/home/amir/boost_1_69_0/doc/html/boost_asio/example/cpp11/multicast/sender.cpp
/home/amir/boost_1_69_0/doc/html/boost_asio/example/cpp11/multicast/receiver.cpp
/home/amir/boost_1_69_0/doc/html/boost_asio/example/cpp11/allocation/server.cpp
/home/amir/boost_1_69_0/doc/html/boost_asio/example/cpp03/buffers/reference_counted.cpp
/home/amir/boost_1_69_0/doc/html/boost_asio/example/cpp03/fork/process_per_connection.cpp
/home/amir/boost_1_69_0/doc/html/boost_asio/example/cpp03/fork/daemon.cpp
/home/amir/boost_1_69_0/doc/html/boost_asio/example/cpp03/spawn/parallel_grep.cpp
/home/amir/boost_1_69_0/doc/html/boost_asio/example/cpp03/spawn/echo_server.cpp
/home/amir/boost_1_69_0/doc/html/boost_asio/example/cpp03/local/stream_server.cpp
/home/amir/boost_1_69_0/doc/html/boost_asio/example/cpp03/local/stream_client.cpp
/home/amir/boost_1_69_0/doc/html/boost_asio/example/cpp03/local/iostream_client.cpp
/home/amir/boost_1_69_0/doc/html/boost_asio/example/cpp03/local/connect_pair.cpp
/home/amir/boost_1_69_0/doc/html/boost_asio/example/cpp03/timers/time_t_timer.cpp
/home/amir/boost_1_69_0/doc/html/boost_asio/example/cpp03/nonblocking/third_party_lib.cpp
/home/amir/boost_1_69_0/doc/html/boost_asio/example/cpp03/porthopper/client.cpp
/home/amir/boost_1_69_0/doc/html/boost_asio/example/cpp03/porthopper/protocol.hpp
/home/amir/boost_1_69_0/doc/html/boost_asio/example/cpp03/porthopper/server.cpp
/home/amir/boost_1_69_0/doc/html/boost_asio/example/cpp03/windows/transmit_file.cpp
/home/amir/boost_1_69_0/doc/html/boost_asio/example/cpp03/services/daytime_client.cpp
/home/amir/boost_1_69_0/doc/html/boost_asio/example/cpp03/services/basic_logger.hpp
/home/amir/boost_1_69_0/doc/html/boost_asio/example/cpp03/services/logger_service.hpp
/home/amir/boost_1_69_0/doc/html/boost_asio/example/cpp03/services/logger_service.cpp
/home/amir/boost_1_69_0/doc/html/boost_asio/example/cpp03/ssl/client.cpp
/home/amir/boost_1_69_0/doc/html/boost_asio/example/cpp03/ssl/server.cpp
/home/amir/boost_1_69_0/doc/html/boost_asio/example/cpp03/socks4/sync_client.cpp
/home/amir/boost_1_69_0/doc/html/boost_asio/example/cpp03/socks4/socks4.hpp
/home/amir/boost_1_69_0/doc/html/boost_asio/example/cpp03/http/server2/io_context_pool.cpp
/home/amir/boost_1_69_0/doc/html/boost_asio/example/cpp03/http/server2/reply.cpp
/home/amir/boost_1_69_0/doc/html/boost_asio/example/cpp03/http/server2/server.hpp
/home/amir/boost_1_69_0/doc/html/boost_asio/example/cpp03/http/server2/connection.cpp
/home/amir/boost_1_69_0/doc/html/boost_asio/example/cpp03/http/server2/io_context_pool.hpp
/home/amir/boost_1_69_0/doc/html/boost_asio/example/cpp03/http/server2/reply.hpp
/home/amir/boost_1_69_0/doc/html/boost_asio/example/cpp03/http/server2/connection.hpp
/home/amir/boost_1_69_0/doc/html/boost_asio/example/cpp03/http/server2/server.cpp
/home/amir/boost_1_69_0/doc/html/boost_asio/example/cpp03/http/server3/reply.cpp
/home/amir/boost_1_69_0/doc/html/boost_asio/example/cpp03/http/server3/server.hpp
/home/amir/boost_1_69_0/doc/html/boost_asio/example/cpp03/http/server3/connection.cpp
/home/amir/boost_1_69_0/doc/html/boost_asio/example/cpp03/http/server3/reply.hpp
/home/amir/boost_1_69_0/doc/html/boost_asio/example/cpp03/http/server3/connection.hpp
/home/amir/boost_1_69_0/doc/html/boost_asio/example/cpp03/http/server3/server.cpp
/home/amir/boost_1_69_0/doc/html/boost_asio/example/cpp03/http/client/sync_client.cpp
/home/amir/boost_1_69_0/doc/html/boost_asio/example/cpp03/http/client/async_client.cpp
/home/amir/boost_1_69_0/doc/html/boost_asio/example/cpp03/http/server/reply.cpp
/home/amir/boost_1_69_0/doc/html/boost_asio/example/cpp03/http/server/server.hpp
/home/amir/boost_1_69_0/doc/html/boost_asio/example/cpp03/http/server/connection.cpp
/home/amir/boost_1_69_0/doc/html/boost_asio/example/cpp03/http/server/reply.hpp
/home/amir/boost_1_69_0/doc/html/boost_asio/example/cpp03/http/server/connection.hpp
/home/amir/boost_1_69_0/doc/html/boost_asio/example/cpp03/http/server/server.cpp
/home/amir/boost_1_69_0/doc/html/boost_asio/example/cpp03/http/server4/reply.cpp
/home/amir/boost_1_69_0/doc/html/boost_asio/example/cpp03/http/server4/server.hpp
/home/amir/boost_1_69_0/doc/html/boost_asio/example/cpp03/http/server4/main.cpp
/home/amir/boost_1_69_0/doc/html/boost_asio/example/cpp03/http/server4/reply.hpp
/home/amir/boost_1_69_0/doc/html/boost_asio/example/cpp03/http/server4/server.cpp
/home/amir/boost_1_69_0/doc/html/boost_asio/example/cpp03/http/server4/request_parser.hpp
/home/amir/boost_1_69_0/doc/html/boost_asio/example/cpp03/chat/chat_server.cpp
/home/amir/boost_1_69_0/doc/html/boost_asio/example/cpp03/chat/chat_client.cpp
/home/amir/boost_1_69_0/doc/html/boost_asio/example/cpp03/chat/posix_chat_client.cpp
/home/amir/boost_1_69_0/doc/html/boost_asio/example/cpp03/timeouts/server.cpp
/home/amir/boost_1_69_0/doc/html/boost_asio/example/cpp03/timeouts/blocking_tcp_client.cpp
/home/amir/boost_1_69_0/doc/html/boost_asio/example/cpp03/timeouts/async_tcp_client.cpp
/home/amir/boost_1_69_0/doc/html/boost_asio/example/cpp03/timeouts/blocking_token_tcp_client.cpp
/home/amir/boost_1_69_0/doc/html/boost_asio/example/cpp03/timeouts/blocking_udp_client.cpp
/home/amir/boost_1_69_0/doc/html/boost_asio/example/cpp03/iostreams/daytime_client.cpp
/home/amir/boost_1_69_0/doc/html/boost_asio/example/cpp03/iostreams/daytime_server.cpp
/home/amir/boost_1_69_0/doc/html/boost_asio/example/cpp03/iostreams/http_client.cpp
/home/amir/boost_1_69_0/doc/html/boost_asio/example/cpp03/serialization/client.cpp
/home/amir/boost_1_69_0/doc/html/boost_asio/example/cpp03/serialization/connection.hpp
/home/amir/boost_1_69_0/doc/html/boost_asio/example/cpp03/serialization/server.cpp
/home/amir/boost_1_69_0/doc/html/boost_asio/example/cpp03/invocation/prioritised_handlers.cpp
/home/amir/boost_1_69_0/doc/html/boost_asio/example/cpp03/echo/blocking_tcp_echo_server.cpp
/home/amir/boost_1_69_0/doc/html/boost_asio/example/cpp03/echo/blocking_tcp_echo_client.cpp
/home/amir/boost_1_69_0/doc/html/boost_asio/example/cpp03/echo/async_tcp_echo_server.cpp
/home/amir/boost_1_69_0/doc/html/boost_asio/example/cpp03/echo/blocking_udp_echo_client.cpp
/home/amir/boost_1_69_0/doc/html/boost_asio/example/cpp03/echo/async_udp_echo_server.cpp
/home/amir/boost_1_69_0/doc/html/boost_asio/example/cpp03/echo/blocking_udp_echo_server.cpp
/home/amir/boost_1_69_0/doc/html/boost_asio/example/cpp03/icmp/ping.cpp
/home/amir/boost_1_69_0/doc/html/boost_asio/example/cpp03/icmp/ipv4_header.hpp
/home/amir/boost_1_69_0/doc/html/boost_asio/example/cpp03/multicast/sender.cpp
/home/amir/boost_1_69_0/doc/html/boost_asio/example/cpp03/multicast/receiver.cpp
/home/amir/boost_1_69_0/doc/html/boost_asio/example/cpp03/allocation/server.cpp
/home/amir/boost_1_69_0/doc/html/boost_asio/index.html
/home/amir/boost_1_69_0/doc/html/boost_asio/net_ts.html
/home/amir/boost_1_69_0/doc/html/boost_asio/reference/spawn.html
/home/amir/boost_1_69_0/doc/html/boost_asio/reference/AcceptHandler.html
/home/amir/boost_1_69_0/doc/html/boost_asio/reference/placeholders__signal_number.html
/home/amir/boost_1_69_0/doc/html/boost_asio/reference/serial_port/async_read_some.html
/home/amir/boost_1_69_0/doc/html/boost_asio/reference/serial_port/serial_port/overload2.html
/home/amir/boost_1_69_0/doc/html/boost_asio/reference/serial_port/serial_port/overload4.html
/home/amir/boost_1_69_0/doc/html/boost_asio/reference/serial_port/serial_port/overload3.html
/home/amir/boost_1_69_0/doc/html/boost_asio/reference/serial_port/serial_port/overload1.html
/home/amir/boost_1_69_0/doc/html/boost_asio/reference/serial_port/close/overload2.html
/home/amir/boost_1_69_0/doc/html/boost_asio/reference/serial_port/close/overload1.html
/home/amir/boost_1_69_0/doc/html/boost_asio/reference/serial_port/write_some/overload1.html
/home/amir/boost_1_69_0/doc/html/boost_asio/reference/serial_port/serial_port.html
/home/amir/boost_1_69_0/doc/html/boost_asio/reference/serial_port/get_io_context.html
/home/amir/boost_1_69_0/doc/html/boost_asio/reference/serial_port/cancel/overload2.html
/home/amir/boost_1_69_0/doc/html/boost_asio/reference/serial_port/cancel/overload1.html
/home/amir/boost_1_69_0/doc/html/boost_asio/reference/serial_port/async_write_some.html
/home/amir/boost_1_69_0/doc/html/boost_asio/reference/serial_port/read_some/overload1.html
/home/amir/boost_1_69_0/doc/html/boost_asio/reference/serial_port/get_io_service.html
/home/amir/boost_1_69_0/doc/html/boost_asio/reference/is_error_code_enum_lt__netdb_errors__gt_.html
/home/amir/boost_1_69_0/doc/html/boost_asio/reference/basic_seq_packet_socket/set_option/overload2.html
/home/amir/boost_1_69_0/doc/html/boost_asio/reference/basic_seq_packet_socket/set_option/overload1.html
/home/amir/boost_1_69_0/doc/html/boost_asio/reference/basic_seq_packet_socket/close/overload2.html
/home/amir/boost_1_69_0/doc/html/boost_asio/reference/basic_seq_packet_socket/close/overload1.html
/home/amir/boost_1_69_0/doc/html/boost_asio/reference/basic_seq_packet_socket/basic_seq_packet_socket/overload2.html
/home/amir/boost_1_69_0/doc/html/boost_asio/reference/basic_seq_packet_socket/basic_seq_packet_socket/overload4.html
/home/amir/boost_1_69_0/doc/html/boost_asio/reference/basic_seq_packet_socket/basic_seq_packet_socket/overload3.html
/home/amir/boost_1_69_0/doc/html/boost_asio/reference/basic_seq_packet_socket/basic_seq_packet_socket/overload1.html
/home/amir/boost_1_69_0/doc/html/boost_asio/reference/basic_seq_packet_socket/async_receive/overload2.html
/home/amir/boost_1_69_0/doc/html/boost_asio/reference/basic_seq_packet_socket/async_receive/overload1.html
/home/amir/boost_1_69_0/doc/html/boost_asio/reference/basic_seq_packet_socket/debug.html
/home/amir/boost_1_69_0/doc/html/boost_asio/reference/basic_seq_packet_socket/get_option/overload2.html
/home/amir/boost_1_69_0/doc/html/boost_asio/reference/basic_seq_packet_socket/get_option/overload1.html
/home/amir/boost_1_69_0/doc/html/boost_asio/reference/basic_seq_packet_socket/receive/overload2.html
/home/amir/boost_1_69_0/doc/html/boost_asio/reference/basic_seq_packet_socket/receive/overload1.html
/home/amir/boost_1_69_0/doc/html/boost_asio/reference/basic_seq_packet_socket/basic_seq_packet_socket.html
/home/amir/boost_1_69_0/doc/html/boost_asio/reference/basic_seq_packet_socket/shutdown/overload2.html
/home/amir/boost_1_69_0/doc/html/boost_asio/reference/basic_seq_packet_socket/shutdown/overload1.html
/home/amir/boost_1_69_0/doc/html/boost_asio/reference/basic_seq_packet_socket/receive_buffer_size.html
/home/amir/boost_1_69_0/doc/html/boost_asio/reference/basic_seq_packet_socket/send_buffer_size.html
/home/amir/boost_1_69_0/doc/html/boost_asio/reference/basic_seq_packet_socket/native_non_blocking/overload2.html
/home/amir/boost_1_69_0/doc/html/boost_asio/reference/basic_seq_packet_socket/native_non_blocking/overload3.html
/home/amir/boost_1_69_0/doc/html/boost_asio/reference/basic_seq_packet_socket/native_non_blocking/overload1.html
/home/amir/boost_1_69_0/doc/html/boost_asio/reference/basic_seq_packet_socket/release/overload2.html
/home/amir/boost_1_69_0/doc/html/boost_asio/reference/basic_seq_packet_socket/release/overload1.html
/home/amir/boost_1_69_0/doc/html/boost_asio/reference/basic_seq_packet_socket/send_low_watermark.html
/home/amir/boost_1_69_0/doc/html/boost_asio/reference/basic_seq_packet_socket/bind/overload2.html
/home/amir/boost_1_69_0/doc/html/boost_asio/reference/basic_seq_packet_socket/bind/overload1.html
/home/amir/boost_1_69_0/doc/html/boost_asio/reference/basic_seq_packet_socket/get_io_context.html
/home/amir/boost_1_69_0/doc/html/boost_asio/reference/basic_seq_packet_socket/connect/overload2.html
/home/amir/boost_1_69_0/doc/html/boost_asio/reference/basic_seq_packet_socket/connect/overload1.html
/home/amir/boost_1_69_0/doc/html/boost_asio/reference/basic_seq_packet_socket/cancel/overload2.html
/home/amir/boost_1_69_0/doc/html/boost_asio/reference/basic_seq_packet_socket/cancel/overload1.html
/home/amir/boost_1_69_0/doc/html/boost_asio/reference/basic_seq_packet_socket/io_control/overload2.html
/home/amir/boost_1_69_0/doc/html/boost_asio/reference/basic_seq_packet_socket/io_control/overload1.html
/home/amir/boost_1_69_0/doc/html/boost_asio/reference/basic_seq_packet_socket/non_blocking/overload2.html
/home/amir/boost_1_69_0/doc/html/boost_asio/reference/basic_seq_packet_socket/non_blocking/overload3.html
/home/amir/boost_1_69_0/doc/html/boost_asio/reference/basic_seq_packet_socket/non_blocking/overload1.html
/home/amir/boost_1_69_0/doc/html/boost_asio/reference/basic_seq_packet_socket/do_not_route.html
/home/amir/boost_1_69_0/doc/html/boost_asio/reference/basic_seq_packet_socket/wait/overload2.html
/home/amir/boost_1_69_0/doc/html/boost_asio/reference/basic_seq_packet_socket/wait/overload1.html
/home/amir/boost_1_69_0/doc/html/boost_asio/reference/basic_seq_packet_socket/local_endpoint/overload2.html
/home/amir/boost_1_69_0/doc/html/boost_asio/reference/basic_seq_packet_socket/local_endpoint/overload1.html
/home/amir/boost_1_69_0/doc/html/boost_asio/reference/basic_seq_packet_socket/keep_alive.html
/home/amir/boost_1_69_0/doc/html/boost_asio/reference/basic_seq_packet_socket/async_send.html
/home/amir/boost_1_69_0/doc/html/boost_asio/reference/basic_seq_packet_socket/async_wait.html
/home/amir/boost_1_69_0/doc/html/boost_asio/reference/basic_seq_packet_socket/out_of_band_inline.html
/home/amir/boost_1_69_0/doc/html/boost_asio/reference/basic_seq_packet_socket/remote_endpoint/overload2.html
/home/amir/boost_1_69_0/doc/html/boost_asio/reference/basic_seq_packet_socket/remote_endpoint/overload1.html
/home/amir/boost_1_69_0/doc/html/boost_asio/reference/basic_seq_packet_socket/reuse_address.html
/home/amir/boost_1_69_0/doc/html/boost_asio/reference/basic_seq_packet_socket/open/overload2.html
/home/amir/boost_1_69_0/doc/html/boost_asio/reference/basic_seq_packet_socket/open/overload1.html
/home/amir/boost_1_69_0/doc/html/boost_asio/reference/basic_seq_packet_socket/async_connect.html
/home/amir/boost_1_69_0/doc/html/boost_asio/reference/basic_seq_packet_socket/linger.html
/home/amir/boost_1_69_0/doc/html/boost_asio/reference/basic_seq_packet_socket/send/overload1.html
/home/amir/boost_1_69_0/doc/html/boost_asio/reference/basic_seq_packet_socket/get_io_service.html
/home/amir/boost_1_69_0/doc/html/boost_asio/reference/basic_seq_packet_socket/bytes_readable.html
/home/amir/boost_1_69_0/doc/html/boost_asio/reference/basic_seq_packet_socket/enable_connection_aborted.html
/home/amir/boost_1_69_0/doc/html/boost_asio/reference/basic_seq_packet_socket/broadcast.html
/home/amir/boost_1_69_0/doc/html/boost_asio/reference/basic_seq_packet_socket/receive_low_watermark.html
/home/amir/boost_1_69_0/doc/html/boost_asio/reference/buffered_stream/get_io_context.html
/home/amir/boost_1_69_0/doc/html/boost_asio/reference/buffered_stream/get_io_service.html
/home/amir/boost_1_69_0/doc/html/boost_asio/reference/error__misc_category.html
/home/amir/boost_1_69_0/doc/html/boost_asio/reference/buffer_size.html
/home/amir/boost_1_69_0/doc/html/boost_asio/reference/read_until/overload14.html
/home/amir/boost_1_69_0/doc/html/boost_asio/reference/read_until/overload16.html
/home/amir/boost_1_69_0/doc/html/boost_asio/reference/read_until/overload9.html
/home/amir/boost_1_69_0/doc/html/boost_asio/reference/read_until/overload7.html
/home/amir/boost_1_69_0/doc/html/boost_asio/reference/read_until/overload5.html
/home/amir/boost_1_69_0/doc/html/boost_asio/reference/read_until/overload3.html
/home/amir/boost_1_69_0/doc/html/boost_asio/reference/read_until/overload11.html
/home/amir/boost_1_69_0/doc/html/boost_asio/reference/read_until/overload15.html
/home/amir/boost_1_69_0/doc/html/boost_asio/reference/read_until/overload1.html
/home/amir/boost_1_69_0/doc/html/boost_asio/reference/read_until/overload13.html
/home/amir/boost_1_69_0/doc/html/boost_asio/reference/read_until/overload10.html
/home/amir/boost_1_69_0/doc/html/boost_asio/reference/read_until/overload12.html
/home/amir/boost_1_69_0/doc/html/boost_asio/reference/BufferedHandshakeHandler.html
/home/amir/boost_1_69_0/doc/html/boost_asio/reference/ConstBufferSequence.html
/home/amir/boost_1_69_0/doc/html/boost_asio/reference/write/overload2.html
/home/amir/boost_1_69_0/doc/html/boost_asio/reference/write/overload9.html
/home/amir/boost_1_69_0/doc/html/boost_asio/reference/write/overload5.html
/home/amir/boost_1_69_0/doc/html/boost_asio/reference/write/overload3.html
/home/amir/boost_1_69_0/doc/html/boost_asio/reference/write/overload1.html
/home/amir/boost_1_69_0/doc/html/boost_asio/reference/write/overload6.html
/home/amir/boost_1_69_0/doc/html/boost_asio/reference/write/overload10.html
/home/amir/boost_1_69_0/doc/html/boost_asio/reference/posix__descriptor/close/overload2.html
/home/amir/boost_1_69_0/doc/html/boost_asio/reference/posix__descriptor/close/overload1.html
/home/amir/boost_1_69_0/doc/html/boost_asio/reference/posix__descriptor/native_non_blocking/overload2.html
/home/amir/boost_1_69_0/doc/html/boost_asio/reference/posix__descriptor/native_non_blocking/overload3.html
/home/amir/boost_1_69_0/doc/html/boost_asio/reference/posix__descriptor/native_non_blocking/overload1.html
/home/amir/boost_1_69_0/doc/html/boost_asio/reference/posix__descriptor/get_io_context.html
/home/amir/boost_1_69_0/doc/html/boost_asio/reference/posix__descriptor/cancel/overload2.html
/home/amir/boost_1_69_0/doc/html/boost_asio/reference/posix__descriptor/cancel/overload1.html
/home/amir/boost_1_69_0/doc/html/boost_asio/reference/posix__descriptor/io_control/overload2.html
/home/amir/boost_1_69_0/doc/html/boost_asio/reference/posix__descriptor/io_control/overload1.html
/home/amir/boost_1_69_0/doc/html/boost_asio/reference/posix__descriptor/non_blocking/overload2.html
/home/amir/boost_1_69_0/doc/html/boost_asio/reference/posix__descriptor/non_blocking/overload3.html
/home/amir/boost_1_69_0/doc/html/boost_asio/reference/posix__descriptor/non_blocking/overload1.html
/home/amir/boost_1_69_0/doc/html/boost_asio/reference/posix__descriptor/wait/overload2.html
/home/amir/boost_1_69_0/doc/html/boost_asio/reference/posix__descriptor/wait/overload1.html
/home/amir/boost_1_69_0/doc/html/boost_asio/reference/posix__descriptor/descriptor/overload2.html
/home/amir/boost_1_69_0/doc/html/boost_asio/reference/posix__descriptor/descriptor/overload1.html
/home/amir/boost_1_69_0/doc/html/boost_asio/reference/posix__descriptor/async_wait.html
/home/amir/boost_1_69_0/doc/html/boost_asio/reference/posix__descriptor/get_io_service.html
/home/amir/boost_1_69_0/doc/html/boost_asio/reference/posix__descriptor/bytes_readable.html
/home/amir/boost_1_69_0/doc/html/boost_asio/reference/posix__descriptor/release.html
/home/amir/boost_1_69_0/doc/html/boost_asio/reference/posix__descriptor/descriptor.html
/home/amir/boost_1_69_0/doc/html/boost_asio/reference/windows__object_handle/close/overload2.html
/home/amir/boost_1_69_0/doc/html/boost_asio/reference/windows__object_handle/close/overload1.html
/home/amir/boost_1_69_0/doc/html/boost_asio/reference/windows__object_handle/object_handle.html
/home/amir/boost_1_69_0/doc/html/boost_asio/reference/windows__object_handle/object_handle/overload2.html
/home/amir/boost_1_69_0/doc/html/boost_asio/reference/windows__object_handle/object_handle/overload1.html
/home/amir/boost_1_69_0/doc/html/boost_asio/reference/windows__object_handle/get_io_context.html
/home/amir/boost_1_69_0/doc/html/boost_asio/reference/windows__object_handle/cancel/overload2.html
/home/amir/boost_1_69_0/doc/html/boost_asio/reference/windows__object_handle/cancel/overload1.html
/home/amir/boost_1_69_0/doc/html/boost_asio/reference/windows__object_handle/async_wait.html
/home/amir/boost_1_69_0/doc/html/boost_asio/reference/windows__object_handle/get_io_service.html
/home/amir/boost_1_69_0/doc/html/boost_asio/reference/thread_pool/make_service.html
/home/amir/boost_1_69_0/doc/html/boost_asio/reference/thread_pool/add_service.html
/home/amir/boost_1_69_0/doc/html/boost_asio/reference/transfer_all.html
/home/amir/boost_1_69_0/doc/html/boost_asio/reference/socket_base/debug.html
/home/amir/boost_1_69_0/doc/html/boost_asio/reference/socket_base/receive_buffer_size.html
/home/amir/boost_1_69_0/doc/html/boost_asio/reference/socket_base/send_buffer_size.html
/home/amir/boost_1_69_0/doc/html/boost_asio/reference/socket_base/send_low_watermark.html
/home/amir/boost_1_69_0/doc/html/boost_asio/reference/socket_base/do_not_route.html
/home/amir/boost_1_69_0/doc/html/boost_asio/reference/socket_base/keep_alive.html
/home/amir/boost_1_69_0/doc/html/boost_asio/reference/socket_base/out_of_band_inline.html
/home/amir/boost_1_69_0/doc/html/boost_asio/reference/socket_base/reuse_address.html
/home/amir/boost_1_69_0/doc/html/boost_asio/reference/socket_base/linger.html
/home/amir/boost_1_69_0/doc/html/boost_asio/reference/socket_base/bytes_readable.html
/home/amir/boost_1_69_0/doc/html/boost_asio/reference/socket_base/enable_connection_aborted.html
/home/amir/boost_1_69_0/doc/html/boost_asio/reference/socket_base/broadcast.html
/home/amir/boost_1_69_0/doc/html/boost_asio/reference/socket_base/receive_low_watermark.html
/home/amir/boost_1_69_0/doc/html/boost_asio/reference/windows__overlapped_handle/close/overload2.html
/home/amir/boost_1_69_0/doc/html/boost_asio/reference/windows__overlapped_handle/close/overload1.html
/home/amir/boost_1_69_0/doc/html/boost_asio/reference/windows__overlapped_handle/overlapped_handle/overload2.html
/home/amir/boost_1_69_0/doc/html/boost_asio/reference/windows__overlapped_handle/overlapped_handle/overload1.html
/home/amir/boost_1_69_0/doc/html/boost_asio/reference/windows__overlapped_handle/get_io_context.html
/home/amir/boost_1_69_0/doc/html/boost_asio/reference/windows__overlapped_handle/cancel/overload2.html
/home/amir/boost_1_69_0/doc/html/boost_asio/reference/windows__overlapped_handle/cancel/overload1.html
/home/amir/boost_1_69_0/doc/html/boost_asio/reference/windows__overlapped_handle/overlapped_handle.html
/home/amir/boost_1_69_0/doc/html/boost_asio/reference/windows__overlapped_handle/get_io_service.html
/home/amir/boost_1_69_0/doc/html/boost_asio/reference/ResolveHandler.html
/home/amir/boost_1_69_0/doc/html/boost_asio/reference/async_completion/completion_handler_type.html
/home/amir/boost_1_69_0/doc/html/boost_asio/reference/basic_stream_socket/async_read_some.html
/home/amir/boost_1_69_0/doc/html/boost_asio/reference/basic_stream_socket/set_option/overload2.html
/home/amir/boost_1_69_0/doc/html/boost_asio/reference/basic_stream_socket/set_option/overload1.html
/home/amir/boost_1_69_0/doc/html/boost_asio/reference/basic_stream_socket/close/overload2.html
/home/amir/boost_1_69_0/doc/html/boost_asio/reference/basic_stream_socket/close/overload1.html
/home/amir/boost_1_69_0/doc/html/boost_asio/reference/basic_stream_socket/basic_stream_socket.html
/home/amir/boost_1_69_0/doc/html/boost_asio/reference/basic_stream_socket/async_receive/overload2.html
/home/amir/boost_1_69_0/doc/html/boost_asio/reference/basic_stream_socket/async_receive/overload1.html
/home/amir/boost_1_69_0/doc/html/boost_asio/reference/basic_stream_socket/debug.html
/home/amir/boost_1_69_0/doc/html/boost_asio/reference/basic_stream_socket/write_some/overload1.html
/home/amir/boost_1_69_0/doc/html/boost_asio/reference/basic_stream_socket/get_option/overload2.html
/home/amir/boost_1_69_0/doc/html/boost_asio/reference/basic_stream_socket/get_option/overload1.html
/home/amir/boost_1_69_0/doc/html/boost_asio/reference/basic_stream_socket/receive/overload2.html
/home/amir/boost_1_69_0/doc/html/boost_asio/reference/basic_stream_socket/receive/overload1.html
/home/amir/boost_1_69_0/doc/html/boost_asio/reference/basic_stream_socket/basic_stream_socket/overload2.html
/home/amir/boost_1_69_0/doc/html/boost_asio/reference/basic_stream_socket/basic_stream_socket/overload4.html
/home/amir/boost_1_69_0/doc/html/boost_asio/reference/basic_stream_socket/basic_stream_socket/overload3.html
/home/amir/boost_1_69_0/doc/html/boost_asio/reference/basic_stream_socket/basic_stream_socket/overload1.html
/home/amir/boost_1_69_0/doc/html/boost_asio/reference/basic_stream_socket/shutdown/overload2.html
/home/amir/boost_1_69_0/doc/html/boost_asio/reference/basic_stream_socket/shutdown/overload1.html
/home/amir/boost_1_69_0/doc/html/boost_asio/reference/basic_stream_socket/receive_buffer_size.html
/home/amir/boost_1_69_0/doc/html/boost_asio/reference/basic_stream_socket/send_buffer_size.html
/home/amir/boost_1_69_0/doc/html/boost_asio/reference/basic_stream_socket/native_non_blocking/overload2.html
/home/amir/boost_1_69_0/doc/html/boost_asio/reference/basic_stream_socket/native_non_blocking/overload3.html
/home/amir/boost_1_69_0/doc/html/boost_asio/reference/basic_stream_socket/native_non_blocking/overload1.html
/home/amir/boost_1_69_0/doc/html/boost_asio/reference/basic_stream_socket/release/overload2.html
/home/amir/boost_1_69_0/doc/html/boost_asio/reference/basic_stream_socket/release/overload1.html
/home/amir/boost_1_69_0/doc/html/boost_asio/reference/basic_stream_socket/send_low_watermark.html
/home/amir/boost_1_69_0/doc/html/boost_asio/reference/basic_stream_socket/bind/overload2.html
/home/amir/boost_1_69_0/doc/html/boost_asio/reference/basic_stream_socket/bind/overload1.html
/home/amir/boost_1_69_0/doc/html/boost_asio/reference/basic_stream_socket/get_io_context.html
/home/amir/boost_1_69_0/doc/html/boost_asio/reference/basic_stream_socket/connect/overload2.html
/home/amir/boost_1_69_0/doc/html/boost_asio/reference/basic_stream_socket/connect/overload1.html
/home/amir/boost_1_69_0/doc/html/boost_asio/reference/basic_stream_socket/cancel/overload2.html
/home/amir/boost_1_69_0/doc/html/boost_asio/reference/basic_stream_socket/cancel/overload1.html
/home/amir/boost_1_69_0/doc/html/boost_asio/reference/basic_stream_socket/io_control/overload2.html
/home/amir/boost_1_69_0/doc/html/boost_asio/reference/basic_stream_socket/io_control/overload1.html
/home/amir/boost_1_69_0/doc/html/boost_asio/reference/basic_stream_socket/non_blocking/overload2.html
/home/amir/boost_1_69_0/doc/html/boost_asio/reference/basic_stream_socket/non_blocking/overload3.html
/home/amir/boost_1_69_0/doc/html/boost_asio/reference/basic_stream_socket/non_blocking/overload1.html
/home/amir/boost_1_69_0/doc/html/boost_asio/reference/basic_stream_socket/do_not_route.html
/home/amir/boost_1_69_0/doc/html/boost_asio/reference/basic_stream_socket/wait/overload2.html
/home/amir/boost_1_69_0/doc/html/boost_asio/reference/basic_stream_socket/wait/overload1.html
/home/amir/boost_1_69_0/doc/html/boost_asio/reference/basic_stream_socket/local_endpoint/overload2.html
/home/amir/boost_1_69_0/doc/html/boost_asio/reference/basic_stream_socket/local_endpoint/overload1.html
/home/amir/boost_1_69_0/doc/html/boost_asio/reference/basic_stream_socket/keep_alive.html
/home/amir/boost_1_69_0/doc/html/boost_asio/reference/basic_stream_socket/async_wait.html
/home/amir/boost_1_69_0/doc/html/boost_asio/reference/basic_stream_socket/out_of_band_inline.html
/home/amir/boost_1_69_0/doc/html/boost_asio/reference/basic_stream_socket/remote_endpoint/overload2.html
/home/amir/boost_1_69_0/doc/html/boost_asio/reference/basic_stream_socket/remote_endpoint/overload1.html
/home/amir/boost_1_69_0/doc/html/boost_asio/reference/basic_stream_socket/async_write_some.html
/home/amir/boost_1_69_0/doc/html/boost_asio/reference/basic_stream_socket/reuse_address.html
/home/amir/boost_1_69_0/doc/html/boost_asio/reference/basic_stream_socket/open/overload2.html
/home/amir/boost_1_69_0/doc/html/boost_asio/reference/basic_stream_socket/open/overload1.html
/home/amir/boost_1_69_0/doc/html/boost_asio/reference/basic_stream_socket/async_connect.html
/home/amir/boost_1_69_0/doc/html/boost_asio/reference/basic_stream_socket/linger.html
/home/amir/boost_1_69_0/doc/html/boost_asio/reference/basic_stream_socket/send/overload2.html
/home/amir/boost_1_69_0/doc/html/boost_asio/reference/basic_stream_socket/send/overload1.html
/home/amir/boost_1_69_0/doc/html/boost_asio/reference/basic_stream_socket/read_some/overload1.html
/home/amir/boost_1_69_0/doc/html/boost_asio/reference/basic_stream_socket/async_send/overload2.html
/home/amir/boost_1_69_0/doc/html/boost_asio/reference/basic_stream_socket/async_send/overload1.html
/home/amir/boost_1_69_0/doc/html/boost_asio/reference/basic_stream_socket/get_io_service.html
/home/amir/boost_1_69_0/doc/html/boost_asio/reference/basic_stream_socket/bytes_readable.html
/home/amir/boost_1_69_0/doc/html/boost_asio/reference/basic_stream_socket/enable_connection_aborted.html
/home/amir/boost_1_69_0/doc/html/boost_asio/reference/basic_stream_socket/broadcast.html
/home/amir/boost_1_69_0/doc/html/boost_asio/reference/basic_stream_socket/receive_low_watermark.html
/home/amir/boost_1_69_0/doc/html/boost_asio/reference/ssl__stream.html
/home/amir/boost_1_69_0/doc/html/boost_asio/reference/windows__stream_handle/async_read_some.html
/home/amir/boost_1_69_0/doc/html/boost_asio/reference/windows__stream_handle/close/overload2.html
/home/amir/boost_1_69_0/doc/html/boost_asio/reference/windows__stream_handle/close/overload1.html
/home/amir/boost_1_69_0/doc/html/boost_asio/reference/windows__stream_handle/write_some/overload1.html
/home/amir/boost_1_69_0/doc/html/boost_asio/reference/windows__stream_handle/stream_handle.html
/home/amir/boost_1_69_0/doc/html/boost_asio/reference/windows__stream_handle/get_io_context.html
/home/amir/boost_1_69_0/doc/html/boost_asio/reference/windows__stream_handle/cancel/overload2.html
/home/amir/boost_1_69_0/doc/html/boost_asio/reference/windows__stream_handle/cancel/overload1.html
/home/amir/boost_1_69_0/doc/html/boost_asio/reference/windows__stream_handle/stream_handle/overload2.html
/home/amir/boost_1_69_0/doc/html/boost_asio/reference/windows__stream_handle/stream_handle/overload1.html
/home/amir/boost_1_69_0/doc/html/boost_asio/reference/windows__stream_handle/async_write_some.html
/home/amir/boost_1_69_0/doc/html/boost_asio/reference/windows__stream_handle/read_some/overload1.html
/home/amir/boost_1_69_0/doc/html/boost_asio/reference/windows__stream_handle/get_io_service.html
/home/amir/boost_1_69_0/doc/html/boost_asio/reference/transfer_at_least.html
/home/amir/boost_1_69_0/doc/html/boost_asio/reference/basic_datagram_socket/set_option/overload2.html
/home/amir/boost_1_69_0/doc/html/boost_asio/reference/basic_datagram_socket/set_option/overload1.html
/home/amir/boost_1_69_0/doc/html/boost_asio/reference/basic_datagram_socket/close/overload2.html
/home/amir/boost_1_69_0/doc/html/boost_asio/reference/basic_datagram_socket/close/overload1.html
/home/amir/boost_1_69_0/doc/html/boost_asio/reference/basic_datagram_socket/async_receive/overload2.html
/home/amir/boost_1_69_0/doc/html/boost_asio/reference/basic_datagram_socket/async_receive/overload1.html
/home/amir/boost_1_69_0/doc/html/boost_asio/reference/basic_datagram_socket/debug.html
/home/amir/boost_1_69_0/doc/html/boost_asio/reference/basic_datagram_socket/get_option/overload2.html
/home/amir/boost_1_69_0/doc/html/boost_asio/reference/basic_datagram_socket/get_option/overload1.html
/home/amir/boost_1_69_0/doc/html/boost_asio/reference/basic_datagram_socket/receive/overload1.html
/home/amir/boost_1_69_0/doc/html/boost_asio/reference/basic_datagram_socket/send_to/overload1.html
/home/amir/boost_1_69_0/doc/html/boost_asio/reference/basic_datagram_socket/basic_datagram_socket/overload2.html
/home/amir/boost_1_69_0/doc/html/boost_asio/reference/basic_datagram_socket/basic_datagram_socket/overload4.html
/home/amir/boost_1_69_0/doc/html/boost_asio/reference/basic_datagram_socket/basic_datagram_socket/overload3.html
/home/amir/boost_1_69_0/doc/html/boost_asio/reference/basic_datagram_socket/basic_datagram_socket/overload1.html
/home/amir/boost_1_69_0/doc/html/boost_asio/reference/basic_datagram_socket/shutdown/overload2.html
/home/amir/boost_1_69_0/doc/html/boost_asio/reference/basic_datagram_socket/shutdown/overload1.html
/home/amir/boost_1_69_0/doc/html/boost_asio/reference/basic_datagram_socket/receive_buffer_size.html
/home/amir/boost_1_69_0/doc/html/boost_asio/reference/basic_datagram_socket/send_buffer_size.html
/home/amir/boost_1_69_0/doc/html/boost_asio/reference/basic_datagram_socket/native_non_blocking/overload2.html
/home/amir/boost_1_69_0/doc/html/boost_asio/reference/basic_datagram_socket/native_non_blocking/overload3.html
/home/amir/boost_1_69_0/doc/html/boost_asio/reference/basic_datagram_socket/native_non_blocking/overload1.html
/home/amir/boost_1_69_0/doc/html/boost_asio/reference/basic_datagram_socket/release/overload2.html
/home/amir/boost_1_69_0/doc/html/boost_asio/reference/basic_datagram_socket/release/overload1.html
/home/amir/boost_1_69_0/doc/html/boost_asio/reference/basic_datagram_socket/send_low_watermark.html
/home/amir/boost_1_69_0/doc/html/boost_asio/reference/basic_datagram_socket/bind/overload2.html
/home/amir/boost_1_69_0/doc/html/boost_asio/reference/basic_datagram_socket/bind/overload1.html
/home/amir/boost_1_69_0/doc/html/boost_asio/reference/basic_datagram_socket/get_io_context.html
/home/amir/boost_1_69_0/doc/html/boost_asio/reference/basic_datagram_socket/connect/overload2.html
/home/amir/boost_1_69_0/doc/html/boost_asio/reference/basic_datagram_socket/connect/overload1.html
/home/amir/boost_1_69_0/doc/html/boost_asio/reference/basic_datagram_socket/basic_datagram_socket.html
/home/amir/boost_1_69_0/doc/html/boost_asio/reference/basic_datagram_socket/cancel/overload2.html
/home/amir/boost_1_69_0/doc/html/boost_asio/reference/basic_datagram_socket/cancel/overload1.html
/home/amir/boost_1_69_0/doc/html/boost_asio/reference/basic_datagram_socket/async_receive_from/overload2.html
/home/amir/boost_1_69_0/doc/html/boost_asio/reference/basic_datagram_socket/async_receive_from/overload1.html
/home/amir/boost_1_69_0/doc/html/boost_asio/reference/basic_datagram_socket/io_control/overload2.html
/home/amir/boost_1_69_0/doc/html/boost_asio/reference/basic_datagram_socket/io_control/overload1.html
/home/amir/boost_1_69_0/doc/html/boost_asio/reference/basic_datagram_socket/non_blocking/overload2.html
/home/amir/boost_1_69_0/doc/html/boost_asio/reference/basic_datagram_socket/non_blocking/overload3.html
/home/amir/boost_1_69_0/doc/html/boost_asio/reference/basic_datagram_socket/non_blocking/overload1.html
/home/amir/boost_1_69_0/doc/html/boost_asio/reference/basic_datagram_socket/do_not_route.html
/home/amir/boost_1_69_0/doc/html/boost_asio/reference/basic_datagram_socket/receive_from/overload1.html
/home/amir/boost_1_69_0/doc/html/boost_asio/reference/basic_datagram_socket/wait/overload2.html
/home/amir/boost_1_69_0/doc/html/boost_asio/reference/basic_datagram_socket/wait/overload1.html
/home/amir/boost_1_69_0/doc/html/boost_asio/reference/basic_datagram_socket/local_endpoint/overload2.html
/home/amir/boost_1_69_0/doc/html/boost_asio/reference/basic_datagram_socket/local_endpoint/overload1.html
/home/amir/boost_1_69_0/doc/html/boost_asio/reference/basic_datagram_socket/keep_alive.html
/home/amir/boost_1_69_0/doc/html/boost_asio/reference/basic_datagram_socket/async_send_to/overload2.html
/home/amir/boost_1_69_0/doc/html/boost_asio/reference/basic_datagram_socket/async_send_to/overload1.html
/home/amir/boost_1_69_0/doc/html/boost_asio/reference/basic_datagram_socket/async_wait.html
/home/amir/boost_1_69_0/doc/html/boost_asio/reference/basic_datagram_socket/out_of_band_inline.html
/home/amir/boost_1_69_0/doc/html/boost_asio/reference/basic_datagram_socket/remote_endpoint/overload2.html
/home/amir/boost_1_69_0/doc/html/boost_asio/reference/basic_datagram_socket/remote_endpoint/overload1.html
/home/amir/boost_1_69_0/doc/html/boost_asio/reference/basic_datagram_socket/reuse_address.html
/home/amir/boost_1_69_0/doc/html/boost_asio/reference/basic_datagram_socket/open/overload2.html
/home/amir/boost_1_69_0/doc/html/boost_asio/reference/basic_datagram_socket/open/overload1.html
/home/amir/boost_1_69_0/doc/html/boost_asio/reference/basic_datagram_socket/async_connect.html
/home/amir/boost_1_69_0/doc/html/boost_asio/reference/basic_datagram_socket/linger.html
/home/amir/boost_1_69_0/doc/html/boost_asio/reference/basic_datagram_socket/send/overload1.html
/home/amir/boost_1_69_0/doc/html/boost_asio/reference/basic_datagram_socket/async_send/overload2.html
/home/amir/boost_1_69_0/doc/html/boost_asio/reference/basic_datagram_socket/async_send/overload1.html
/home/amir/boost_1_69_0/doc/html/boost_asio/reference/basic_datagram_socket/get_io_service.html
/home/amir/boost_1_69_0/doc/html/boost_asio/reference/basic_datagram_socket/bytes_readable.html
/home/amir/boost_1_69_0/doc/html/boost_asio/reference/basic_datagram_socket/enable_connection_aborted.html
/home/amir/boost_1_69_0/doc/html/boost_asio/reference/basic_datagram_socket/broadcast.html
/home/amir/boost_1_69_0/doc/html/boost_asio/reference/basic_datagram_socket/receive_low_watermark.html
/home/amir/boost_1_69_0/doc/html/boost_asio/reference/async_read_until.html
/home/amir/boost_1_69_0/doc/html/boost_asio/reference/io_context__strand/context.html
/home/amir/boost_1_69_0/doc/html/boost_asio/reference/io_context__strand/strand.html
/home/amir/boost_1_69_0/doc/html/boost_asio/reference/io_context__strand/get_io_context.html
/home/amir/boost_1_69_0/doc/html/boost_asio/reference/io_context__strand/get_io_service.html
/home/amir/boost_1_69_0/doc/html/boost_asio/reference/basic_socket/set_option/overload2.html
/home/amir/boost_1_69_0/doc/html/boost_asio/reference/basic_socket/set_option/overload1.html
/home/amir/boost_1_69_0/doc/html/boost_asio/reference/basic_socket/close/overload2.html
/home/amir/boost_1_69_0/doc/html/boost_asio/reference/basic_socket/close/overload1.html
/home/amir/boost_1_69_0/doc/html/boost_asio/reference/basic_socket/basic_socket.html
/home/amir/boost_1_69_0/doc/html/boost_asio/reference/basic_socket/debug.html
/home/amir/boost_1_69_0/doc/html/boost_asio/reference/basic_socket/get_option/overload2.html
/home/amir/boost_1_69_0/doc/html/boost_asio/reference/basic_socket/get_option/overload1.html
/home/amir/boost_1_69_0/doc/html/boost_asio/reference/basic_socket/shutdown/overload2.html
/home/amir/boost_1_69_0/doc/html/boost_asio/reference/basic_socket/shutdown/overload1.html
/home/amir/boost_1_69_0/doc/html/boost_asio/reference/basic_socket/basic_socket/overload2.html
/home/amir/boost_1_69_0/doc/html/boost_asio/reference/basic_socket/basic_socket/overload4.html
/home/amir/boost_1_69_0/doc/html/boost_asio/reference/basic_socket/basic_socket/overload3.html
/home/amir/boost_1_69_0/doc/html/boost_asio/reference/basic_socket/basic_socket/overload1.html
/home/amir/boost_1_69_0/doc/html/boost_asio/reference/basic_socket/receive_buffer_size.html
/home/amir/boost_1_69_0/doc/html/boost_asio/reference/basic_socket/send_buffer_size.html
/home/amir/boost_1_69_0/doc/html/boost_asio/reference/basic_socket/native_non_blocking/overload2.html
/home/amir/boost_1_69_0/doc/html/boost_asio/reference/basic_socket/native_non_blocking/overload3.html
/home/amir/boost_1_69_0/doc/html/boost_asio/reference/basic_socket/native_non_blocking/overload1.html
/home/amir/boost_1_69_0/doc/html/boost_asio/reference/basic_socket/release/overload2.html
/home/amir/boost_1_69_0/doc/html/boost_asio/reference/basic_socket/release/overload1.html
/home/amir/boost_1_69_0/doc/html/boost_asio/reference/basic_socket/send_low_watermark.html
/home/amir/boost_1_69_0/doc/html/boost_asio/reference/basic_socket/bind/overload2.html
/home/amir/boost_1_69_0/doc/html/boost_asio/reference/basic_socket/bind/overload1.html
/home/amir/boost_1_69_0/doc/html/boost_asio/reference/basic_socket/get_io_context.html
/home/amir/boost_1_69_0/doc/html/boost_asio/reference/basic_socket/connect/overload2.html
/home/amir/boost_1_69_0/doc/html/boost_asio/reference/basic_socket/connect/overload1.html
/home/amir/boost_1_69_0/doc/html/boost_asio/reference/basic_socket/cancel/overload2.html
/home/amir/boost_1_69_0/doc/html/boost_asio/reference/basic_socket/cancel/overload1.html
/home/amir/boost_1_69_0/doc/html/boost_asio/reference/basic_socket/io_control/overload2.html
/home/amir/boost_1_69_0/doc/html/boost_asio/reference/basic_socket/io_control/overload1.html
/home/amir/boost_1_69_0/doc/html/boost_asio/reference/basic_socket/non_blocking/overload2.html
/home/amir/boost_1_69_0/doc/html/boost_asio/reference/basic_socket/non_blocking/overload3.html
/home/amir/boost_1_69_0/doc/html/boost_asio/reference/basic_socket/non_blocking/overload1.html
/home/amir/boost_1_69_0/doc/html/boost_asio/reference/basic_socket/do_not_route.html
/home/amir/boost_1_69_0/doc/html/boost_asio/reference/basic_socket/wait/overload2.html
/home/amir/boost_1_69_0/doc/html/boost_asio/reference/basic_socket/wait/overload1.html
/home/amir/boost_1_69_0/doc/html/boost_asio/reference/basic_socket/local_endpoint/overload2.html
/home/amir/boost_1_69_0/doc/html/boost_asio/reference/basic_socket/local_endpoint/overload1.html
/home/amir/boost_1_69_0/doc/html/boost_asio/reference/basic_socket/keep_alive.html
/home/amir/boost_1_69_0/doc/html/boost_asio/reference/basic_socket/async_wait.html
/home/amir/boost_1_69_0/doc/html/boost_asio/reference/basic_socket/out_of_band_inline.html
/home/amir/boost_1_69_0/doc/html/boost_asio/reference/basic_socket/remote_endpoint/overload2.html
/home/amir/boost_1_69_0/doc/html/boost_asio/reference/basic_socket/remote_endpoint/overload1.html
/home/amir/boost_1_69_0/doc/html/boost_asio/reference/basic_socket/reuse_address.html
/home/amir/boost_1_69_0/doc/html/boost_asio/reference/basic_socket/open/overload2.html
/home/amir/boost_1_69_0/doc/html/boost_asio/reference/basic_socket/open/overload1.html
/home/amir/boost_1_69_0/doc/html/boost_asio/reference/basic_socket/async_connect.html
/home/amir/boost_1_69_0/doc/html/boost_asio/reference/basic_socket/linger.html
/home/amir/boost_1_69_0/doc/html/boost_asio/reference/basic_socket/get_io_service.html
/home/amir/boost_1_69_0/doc/html/boost_asio/reference/basic_socket/bytes_readable.html
/home/amir/boost_1_69_0/doc/html/boost_asio/reference/basic_socket/enable_connection_aborted.html
/home/amir/boost_1_69_0/doc/html/boost_asio/reference/basic_socket/broadcast.html
/home/amir/boost_1_69_0/doc/html/boost_asio/reference/basic_socket/receive_low_watermark.html
/home/amir/boost_1_69_0/doc/html/boost_asio/reference/ip__basic_endpoint/address.html
/home/amir/boost_1_69_0/doc/html/boost_asio/reference/ip__basic_endpoint/basic_endpoint.html
/home/amir/boost_1_69_0/doc/html/boost_asio/reference/ip__basic_endpoint/address/overload2.html
/home/amir/boost_1_69_0/doc/html/boost_asio/reference/ip__basic_endpoint/address/overload1.html
/home/amir/boost_1_69_0/doc/html/boost_asio/reference/ip__basic_endpoint/basic_endpoint/overload2.html
/home/amir/boost_1_69_0/doc/html/boost_asio/reference/ip__basic_endpoint/basic_endpoint/overload3.html
/home/amir/boost_1_69_0/doc/html/boost_asio/reference/is_error_code_enum_lt__basic_errors__gt_.html
/home/amir/boost_1_69_0/doc/html/boost_asio/reference/io_context__service/get_io_context.html
/home/amir/boost_1_69_0/doc/html/boost_asio/reference/io_context__service/service.html
/home/amir/boost_1_69_0/doc/html/boost_asio/reference/io_context__service/get_io_service.html
/home/amir/boost_1_69_0/doc/html/boost_asio/reference/mutable_buffers_1/value_type.html
/home/amir/boost_1_69_0/doc/html/boost_asio/reference/basic_waitable_timer/basic_waitable_timer/overload2.html
/home/amir/boost_1_69_0/doc/html/boost_asio/reference/basic_waitable_timer/basic_waitable_timer/overload3.html
/home/amir/boost_1_69_0/doc/html/boost_asio/reference/basic_waitable_timer/basic_waitable_timer/overload1.html
/home/amir/boost_1_69_0/doc/html/boost_asio/reference/basic_waitable_timer/get_io_context.html
/home/amir/boost_1_69_0/doc/html/boost_asio/reference/basic_waitable_timer/cancel/overload2.html
/home/amir/boost_1_69_0/doc/html/boost_asio/reference/basic_waitable_timer/cancel/overload1.html
/home/amir/boost_1_69_0/doc/html/boost_asio/reference/basic_waitable_timer/expires_from_now/overload2.html
/home/amir/boost_1_69_0/doc/html/boost_asio/reference/basic_waitable_timer/expires_from_now/overload3.html
/home/amir/boost_1_69_0/doc/html/boost_asio/reference/basic_waitable_timer/basic_waitable_timer.html
/home/amir/boost_1_69_0/doc/html/boost_asio/reference/basic_waitable_timer/async_wait.html
/home/amir/boost_1_69_0/doc/html/boost_asio/reference/basic_waitable_timer/expires_after.html
/home/amir/boost_1_69_0/doc/html/boost_asio/reference/basic_waitable_timer/get_io_service.html
/home/amir/boost_1_69_0/doc/html/boost_asio/reference/basic_waitable_timer/cancel_one/overload2.html
/home/amir/boost_1_69_0/doc/html/boost_asio/reference/basic_waitable_timer/cancel_one/overload1.html
/home/amir/boost_1_69_0/doc/html/boost_asio/reference/basic_waitable_timer/expires_at/overload2.html
/home/amir/boost_1_69_0/doc/html/boost_asio/reference/basic_waitable_timer/expires_at/overload3.html
/home/amir/boost_1_69_0/doc/html/boost_asio/reference/is_error_code_enum_lt__ssl_errors__gt_/value.html
/home/amir/boost_1_69_0/doc/html/boost_asio/reference/posix__stream_descriptor/async_read_some.html
/home/amir/boost_1_69_0/doc/html/boost_asio/reference/posix__stream_descriptor/close/overload2.html
/home/amir/boost_1_69_0/doc/html/boost_asio/reference/posix__stream_descriptor/close/overload1.html
/home/amir/boost_1_69_0/doc/html/boost_asio/reference/posix__stream_descriptor/write_some/overload1.html
/home/amir/boost_1_69_0/doc/html/boost_asio/reference/posix__stream_descriptor/stream_descriptor/overload2.html
/home/amir/boost_1_69_0/doc/html/boost_asio/reference/posix__stream_descriptor/stream_descriptor/overload1.html
/home/amir/boost_1_69_0/doc/html/boost_asio/reference/posix__stream_descriptor/stream_descriptor.html
/home/amir/boost_1_69_0/doc/html/boost_asio/reference/posix__stream_descriptor/native_non_blocking/overload2.html
/home/amir/boost_1_69_0/doc/html/boost_asio/reference/posix__stream_descriptor/native_non_blocking/overload3.html
/home/amir/boost_1_69_0/doc/html/boost_asio/reference/posix__stream_descriptor/native_non_blocking/overload1.html
/home/amir/boost_1_69_0/doc/html/boost_asio/reference/posix__stream_descriptor/get_io_context.html
/home/amir/boost_1_69_0/doc/html/boost_asio/reference/posix__stream_descriptor/cancel/overload2.html
/home/amir/boost_1_69_0/doc/html/boost_asio/reference/posix__stream_descriptor/cancel/overload1.html
/home/amir/boost_1_69_0/doc/html/boost_asio/reference/posix__stream_descriptor/io_control/overload2.html
/home/amir/boost_1_69_0/doc/html/boost_asio/reference/posix__stream_descriptor/io_control/overload1.html
/home/amir/boost_1_69_0/doc/html/boost_asio/reference/posix__stream_descriptor/non_blocking/overload2.html
/home/amir/boost_1_69_0/doc/html/boost_asio/reference/posix__stream_descriptor/non_blocking/overload3.html
/home/amir/boost_1_69_0/doc/html/boost_asio/reference/posix__stream_descriptor/non_blocking/overload1.html
/home/amir/boost_1_69_0/doc/html/boost_asio/reference/posix__stream_descriptor/wait/overload2.html
/home/amir/boost_1_69_0/doc/html/boost_asio/reference/posix__stream_descriptor/wait/overload1.html
/home/amir/boost_1_69_0/doc/html/boost_asio/reference/posix__stream_descriptor/async_wait.html
/home/amir/boost_1_69_0/doc/html/boost_asio/reference/posix__stream_descriptor/async_write_some.html
/home/amir/boost_1_69_0/doc/html/boost_asio/reference/posix__stream_descriptor/read_some/overload1.html
/home/amir/boost_1_69_0/doc/html/boost_asio/reference/posix__stream_descriptor/get_io_service.html
/home/amir/boost_1_69_0/doc/html/boost_asio/reference/posix__stream_descriptor/bytes_readable.html
/home/amir/boost_1_69_0/doc/html/boost_asio/reference/posix__stream_descriptor/release.html
/home/amir/boost_1_69_0/doc/html/boost_asio/reference/ip__multicast__leave_group.html
/home/amir/boost_1_69_0/doc/html/boost_asio/reference/spawn/overload6.html
/home/amir/boost_1_69_0/doc/html/boost_asio/reference/dynamic_string_buffer/const_buffers_type.html
/home/amir/boost_1_69_0/doc/html/boost_asio/reference/dynamic_string_buffer/mutable_buffers_type.html
/home/amir/boost_1_69_0/doc/html/boost_asio/reference/null_buffers/value_type.html
/home/amir/boost_1_69_0/doc/html/boost_asio/reference/io_context__work/work.html
/home/amir/boost_1_69_0/doc/html/boost_asio/reference/io_context__work/get_io_context.html
/home/amir/boost_1_69_0/doc/html/boost_asio/reference/io_context__work/get_io_service.html
/home/amir/boost_1_69_0/doc/html/boost_asio/reference/io_context__work/work/overload1.html
/home/amir/boost_1_69_0/doc/html/boost_asio/reference/ConnectHandler.html
/home/amir/boost_1_69_0/doc/html/boost_asio/reference/generic__raw_protocol.html
/home/amir/boost_1_69_0/doc/html/boost_asio/reference/connect/overload2.html
/home/amir/boost_1_69_0/doc/html/boost_asio/reference/connect/overload9.html
/home/amir/boost_1_69_0/doc/html/boost_asio/reference/connect/overload4.html
/home/amir/boost_1_69_0/doc/html/boost_asio/reference/connect/overload7.html
/home/amir/boost_1_69_0/doc/html/boost_asio/reference/connect/overload5.html
/home/amir/boost_1_69_0/doc/html/boost_asio/reference/connect/overload3.html
/home/amir/boost_1_69_0/doc/html/boost_asio/reference/connect/overload11.html
/home/amir/boost_1_69_0/doc/html/boost_asio/reference/connect/overload1.html
/home/amir/boost_1_69_0/doc/html/boost_asio/reference/connect/overload6.html
/home/amir/boost_1_69_0/doc/html/boost_asio/reference/connect/overload8.html
/home/amir/boost_1_69_0/doc/html/boost_asio/reference/connect/overload10.html
/home/amir/boost_1_69_0/doc/html/boost_asio/reference/connect/overload12.html
/home/amir/boost_1_69_0/doc/html/boost_asio/reference/basic_deadline_timer/get_io_context.html
/home/amir/boost_1_69_0/doc/html/boost_asio/reference/basic_deadline_timer/basic_deadline_timer/overload2.html
/home/amir/boost_1_69_0/doc/html/boost_asio/reference/basic_deadline_timer/basic_deadline_timer/overload3.html
/home/amir/boost_1_69_0/doc/html/boost_asio/reference/basic_deadline_timer/basic_deadline_timer/overload1.html
/home/amir/boost_1_69_0/doc/html/boost_asio/reference/basic_deadline_timer/cancel/overload2.html
/home/amir/boost_1_69_0/doc/html/boost_asio/reference/basic_deadline_timer/cancel/overload1.html
/home/amir/boost_1_69_0/doc/html/boost_asio/reference/basic_deadline_timer/expires_from_now/overload2.html
/home/amir/boost_1_69_0/doc/html/boost_asio/reference/basic_deadline_timer/expires_from_now/overload3.html
/home/amir/boost_1_69_0/doc/html/boost_asio/reference/basic_deadline_timer/async_wait.html
/home/amir/boost_1_69_0/doc/html/boost_asio/reference/basic_deadline_timer/basic_deadline_timer.html
/home/amir/boost_1_69_0/doc/html/boost_asio/reference/basic_deadline_timer/get_io_service.html
/home/amir/boost_1_69_0/doc/html/boost_asio/reference/basic_deadline_timer/cancel_one/overload2.html
/home/amir/boost_1_69_0/doc/html/boost_asio/reference/basic_deadline_timer/cancel_one/overload1.html
/home/amir/boost_1_69_0/doc/html/boost_asio/reference/basic_deadline_timer/expires_at/overload2.html
/home/amir/boost_1_69_0/doc/html/boost_asio/reference/basic_deadline_timer/expires_at/overload3.html
/home/amir/boost_1_69_0/doc/html/boost_asio/reference/dynamic_buffer.html
/home/amir/boost_1_69_0/doc/html/boost_asio/reference/ReadHandler.html
/home/amir/boost_1_69_0/doc/html/boost_asio/reference/ssl__rfc2818_verification.html
/home/amir/boost_1_69_0/doc/html/boost_asio/reference/ip__multicast__outbound_interface.html
/home/amir/boost_1_69_0/doc/html/boost_asio/reference/ip__multicast__join_group.html
/home/amir/boost_1_69_0/doc/html/boost_asio/reference/is_error_code_enum_lt__netdb_errors__gt_/value.html
/home/amir/boost_1_69_0/doc/html/boost_asio/reference/async_write/overload2.html
/home/amir/boost_1_69_0/doc/html/boost_asio/reference/async_write/overload4.html
/home/amir/boost_1_69_0/doc/html/boost_asio/reference/async_write/overload5.html
/home/amir/boost_1_69_0/doc/html/boost_asio/reference/async_write/overload3.html
/home/amir/boost_1_69_0/doc/html/boost_asio/reference/async_write/overload1.html
/home/amir/boost_1_69_0/doc/html/boost_asio/reference/async_write/overload6.html
/home/amir/boost_1_69_0/doc/html/boost_asio/reference/is_error_code_enum_lt__addrinfo_errors__gt_/value.html
/home/amir/boost_1_69_0/doc/html/boost_asio/reference/is_error_code_enum_lt__ssl_errors__gt_.html
/home/amir/boost_1_69_0/doc/html/boost_asio/reference/steady_timer.html
/home/amir/boost_1_69_0/doc/html/boost_asio/reference/deadline_timer.html
/home/amir/boost_1_69_0/doc/html/boost_asio/reference/generic__datagram_protocol.html
/home/amir/boost_1_69_0/doc/html/boost_asio/reference/basic_socket_iostream/expires_from_now/overload2.html
/home/amir/boost_1_69_0/doc/html/boost_asio/reference/basic_socket_iostream/expires_after.html
/home/amir/boost_1_69_0/doc/html/boost_asio/reference/basic_socket_iostream/expires_at/overload2.html
/home/amir/boost_1_69_0/doc/html/boost_asio/reference/WaitHandler.html
/home/amir/boost_1_69_0/doc/html/boost_asio/reference/read/overload2.html
/home/amir/boost_1_69_0/doc/html/boost_asio/reference/read/overload9.html
/home/amir/boost_1_69_0/doc/html/boost_asio/reference/read/overload5.html
/home/amir/boost_1_69_0/doc/html/boost_asio/reference/read/overload3.html
/home/amir/boost_1_69_0/doc/html/boost_asio/reference/read/overload1.html
/home/amir/boost_1_69_0/doc/html/boost_asio/reference/read/overload6.html
/home/amir/boost_1_69_0/doc/html/boost_asio/reference/read/overload10.html
/home/amir/boost_1_69_0/doc/html/boost_asio/reference/SignalHandler.html
/home/amir/boost_1_69_0/doc/html/boost_asio/reference/basic_waitable_timer.html
/home/amir/boost_1_69_0/doc/html/boost_asio/reference/buffered_write_stream/get_io_context.html
/home/amir/boost_1_69_0/doc/html/boost_asio/reference/buffered_write_stream/get_io_service.html
/home/amir/boost_1_69_0/doc/html/boost_asio/reference/error__netdb_category.html
/home/amir/boost_1_69_0/doc/html/boost_asio/reference/ip__unicast__hops.html
/home/amir/boost_1_69_0/doc/html/boost_asio/reference/ssl__stream/native_handle.html
/home/amir/boost_1_69_0/doc/html/boost_asio/reference/ssl__stream/get_io_context.html
/home/amir/boost_1_69_0/doc/html/boost_asio/reference/ssl__stream/get_io_service.html
/home/amir/boost_1_69_0/doc/html/boost_asio/reference/buffer_copy.html
/home/amir/boost_1_69_0/doc/html/boost_asio/reference/mutable_buffer.html
/home/amir/boost_1_69_0/doc/html/boost_asio/reference/async_read_until/overload2.html
/home/amir/boost_1_69_0/doc/html/boost_asio/reference/async_read_until/overload4.html
/home/amir/boost_1_69_0/doc/html/boost_asio/reference/async_read_until/overload7.html
/home/amir/boost_1_69_0/doc/html/boost_asio/reference/async_read_until/overload5.html
/home/amir/boost_1_69_0/doc/html/boost_asio/reference/async_read_until/overload3.html
/home/amir/boost_1_69_0/doc/html/boost_asio/reference/async_read_until/overload1.html
/home/amir/boost_1_69_0/doc/html/boost_asio/reference/async_read_until/overload6.html
/home/amir/boost_1_69_0/doc/html/boost_asio/reference/async_read_until/overload8.html
/home/amir/boost_1_69_0/doc/html/boost_asio/reference/async_read_at/overload2.html
/home/amir/boost_1_69_0/doc/html/boost_asio/reference/async_read_at/overload4.html
/home/amir/boost_1_69_0/doc/html/boost_asio/reference/async_read_at/overload3.html
/home/amir/boost_1_69_0/doc/html/boost_asio/reference/async_read_at/overload1.html
/home/amir/boost_1_69_0/doc/html/boost_asio/reference/execution_context/make_service.html
/home/amir/boost_1_69_0/doc/html/boost_asio/reference/execution_context/add_service.html
/home/amir/boost_1_69_0/doc/html/boost_asio/reference/buffer_sequence_begin.html
/home/amir/boost_1_69_0/doc/html/boost_asio/reference/ip__multicast__hops.html
/home/amir/boost_1_69_0/doc/html/boost_asio/reference/buffered_read_stream/get_io_context.html
/home/amir/boost_1_69_0/doc/html/boost_asio/reference/buffered_read_stream/get_io_service.html
/home/amir/boost_1_69_0/doc/html/boost_asio/reference/ip__address/operator_eq_.html
/home/amir/boost_1_69_0/doc/html/boost_asio/reference/ip__address/address.html
/home/amir/boost_1_69_0/doc/html/boost_asio/reference/ip__address/address/overload2.html
/home/amir/boost_1_69_0/doc/html/boost_asio/reference/ip__address/address/overload3.html
/home/amir/boost_1_69_0/doc/html/boost_asio/reference/ip__address/to_v4.html
/home/amir/boost_1_69_0/doc/html/boost_asio/reference/ip__address/operator_eq_/overload2.html
/home/amir/boost_1_69_0/doc/html/boost_asio/reference/ip__address/operator_eq_/overload3.html
/home/amir/boost_1_69_0/doc/html/boost_asio/reference/ip__address/to_v6.html
/home/amir/boost_1_69_0/doc/html/boost_asio/reference/yield_context.html
/home/amir/boost_1_69_0/doc/html/boost_asio/reference/thread_pool.html
/home/amir/boost_1_69_0/doc/html/boost_asio/reference/error__addrinfo_category.html
/home/amir/boost_1_69_0/doc/html/boost_asio/reference/signal_set.html
/home/amir/boost_1_69_0/doc/html/boost_asio/reference/local__stream_protocol/acceptor.html
/home/amir/boost_1_69_0/doc/html/boost_asio/reference/placeholders__iterator.html
/home/amir/boost_1_69_0/doc/html/boost_asio/reference/async_write_at/overload2.html
/home/amir/boost_1_69_0/doc/html/boost_asio/reference/async_write_at/overload4.html
/home/amir/boost_1_69_0/doc/html/boost_asio/reference/async_write_at/overload3.html
/home/amir/boost_1_69_0/doc/html/boost_asio/reference/async_write_at/overload1.html
/home/amir/boost_1_69_0/doc/html/boost_asio/reference/async_connect/overload2.html
/home/amir/boost_1_69_0/doc/html/boost_asio/reference/async_connect/overload4.html
/home/amir/boost_1_69_0/doc/html/boost_asio/reference/async_connect/overload5.html
/home/amir/boost_1_69_0/doc/html/boost_asio/reference/async_connect/overload3.html
/home/amir/boost_1_69_0/doc/html/boost_asio/reference/async_connect/overload1.html
/home/amir/boost_1_69_0/doc/html/boost_asio/reference/async_connect/overload6.html
/home/amir/boost_1_69_0/doc/html/boost_asio/reference/async_read/overload2.html
/home/amir/boost_1_69_0/doc/html/boost_asio/reference/async_read/overload4.html
/home/amir/boost_1_69_0/doc/html/boost_asio/reference/async_read/overload5.html
/home/amir/boost_1_69_0/doc/html/boost_asio/reference/async_read/overload3.html
/home/amir/boost_1_69_0/doc/html/boost_asio/reference/async_read/overload1.html
/home/amir/boost_1_69_0/doc/html/boost_asio/reference/async_read/overload6.html
/home/amir/boost_1_69_0/doc/html/boost_asio/reference/buffer_cast.html
/home/amir/boost_1_69_0/doc/html/boost_asio/reference/is_error_code_enum_lt__addrinfo_errors__gt_.html
/home/amir/boost_1_69_0/doc/html/boost_asio/reference/dynamic_vector_buffer/const_buffers_type.html
/home/amir/boost_1_69_0/doc/html/boost_asio/reference/dynamic_vector_buffer/mutable_buffers_type.html
/home/amir/boost_1_69_0/doc/html/boost_asio/reference/basic_socket_acceptor.html
/home/amir/boost_1_69_0/doc/html/boost_asio/reference/buffer.html
/home/amir/boost_1_69_0/doc/html/boost_asio/reference/WriteHandler.html
/home/amir/boost_1_69_0/doc/html/boost_asio/reference/ip__v6_only.html
/home/amir/boost_1_69_0/doc/html/boost_asio/reference/write_at/overload2.html
/home/amir/boost_1_69_0/doc/html/boost_asio/reference/write_at/overload5.html
/home/amir/boost_1_69_0/doc/html/boost_asio/reference/write_at/overload3.html
/home/amir/boost_1_69_0/doc/html/boost_asio/reference/write_at/overload1.html
/home/amir/boost_1_69_0/doc/html/boost_asio/reference/write_at/overload6.html
/home/amir/boost_1_69_0/doc/html/boost_asio/reference/MutableBufferSequence.html
/home/amir/boost_1_69_0/doc/html/boost_asio/reference/ip__basic_resolver_query/hints.html
/home/amir/boost_1_69_0/doc/html/boost_asio/reference/ip__multicast__enable_loopback.html
/home/amir/boost_1_69_0/doc/html/boost_asio/reference/const_buffers_1/value_type.html
/home/amir/boost_1_69_0/doc/html/boost_asio/reference/basic_socket_acceptor/set_option/overload2.html
/home/amir/boost_1_69_0/doc/html/boost_asio/reference/basic_socket_acceptor/set_option/overload1.html
/home/amir/boost_1_69_0/doc/html/boost_asio/reference/basic_socket_acceptor/close/overload2.html
/home/amir/boost_1_69_0/doc/html/boost_asio/reference/basic_socket_acceptor/debug.html
/home/amir/boost_1_69_0/doc/html/boost_asio/reference/basic_socket_acceptor/get_option/overload2.html
/home/amir/boost_1_69_0/doc/html/boost_asio/reference/basic_socket_acceptor/get_option/overload1.html
/home/amir/boost_1_69_0/doc/html/boost_asio/reference/basic_socket_acceptor/accept.html
/home/amir/boost_1_69_0/doc/html/boost_asio/reference/basic_socket_acceptor/listen/overload2.html
/home/amir/boost_1_69_0/doc/html/boost_asio/reference/basic_socket_acceptor/receive_buffer_size.html
/home/amir/boost_1_69_0/doc/html/boost_asio/reference/basic_socket_acceptor/send_buffer_size.html
/home/amir/boost_1_69_0/doc/html/boost_asio/reference/basic_socket_acceptor/native_non_blocking/overload2.html
/home/amir/boost_1_69_0/doc/html/boost_asio/reference/basic_socket_acceptor/native_non_blocking/overload3.html
/home/amir/boost_1_69_0/doc/html/boost_asio/reference/basic_socket_acceptor/native_non_blocking/overload1.html
/home/amir/boost_1_69_0/doc/html/boost_asio/reference/basic_socket_acceptor/release/overload2.html
/home/amir/boost_1_69_0/doc/html/boost_asio/reference/basic_socket_acceptor/release/overload1.html
/home/amir/boost_1_69_0/doc/html/boost_asio/reference/basic_socket_acceptor/send_low_watermark.html
/home/amir/boost_1_69_0/doc/html/boost_asio/reference/basic_socket_acceptor/bind/overload2.html
/home/amir/boost_1_69_0/doc/html/boost_asio/reference/basic_socket_acceptor/bind/overload1.html
/home/amir/boost_1_69_0/doc/html/boost_asio/reference/basic_socket_acceptor/get_io_context.html
/home/amir/boost_1_69_0/doc/html/boost_asio/reference/basic_socket_acceptor/async_accept/overload2.html
/home/amir/boost_1_69_0/doc/html/boost_asio/reference/basic_socket_acceptor/async_accept/overload4.html
/home/amir/boost_1_69_0/doc/html/boost_asio/reference/basic_socket_acceptor/async_accept/overload5.html
/home/amir/boost_1_69_0/doc/html/boost_asio/reference/basic_socket_acceptor/async_accept/overload3.html
/home/amir/boost_1_69_0/doc/html/boost_asio/reference/basic_socket_acceptor/async_accept/overload1.html
/home/amir/boost_1_69_0/doc/html/boost_asio/reference/basic_socket_acceptor/async_accept/overload6.html
/home/amir/boost_1_69_0/doc/html/boost_asio/reference/basic_socket_acceptor/cancel/overload2.html
/home/amir/boost_1_69_0/doc/html/boost_asio/reference/basic_socket_acceptor/cancel/overload1.html
/home/amir/boost_1_69_0/doc/html/boost_asio/reference/basic_socket_acceptor/io_control/overload2.html
/home/amir/boost_1_69_0/doc/html/boost_asio/reference/basic_socket_acceptor/io_control/overload1.html
/home/amir/boost_1_69_0/doc/html/boost_asio/reference/basic_socket_acceptor/non_blocking/overload2.html
/home/amir/boost_1_69_0/doc/html/boost_asio/reference/basic_socket_acceptor/non_blocking/overload3.html
/home/amir/boost_1_69_0/doc/html/boost_asio/reference/basic_socket_acceptor/non_blocking/overload1.html
/home/amir/boost_1_69_0/doc/html/boost_asio/reference/basic_socket_acceptor/do_not_route.html
/home/amir/boost_1_69_0/doc/html/boost_asio/reference/basic_socket_acceptor/wait/overload2.html
/home/amir/boost_1_69_0/doc/html/boost_asio/reference/basic_socket_acceptor/wait/overload1.html
/home/amir/boost_1_69_0/doc/html/boost_asio/reference/basic_socket_acceptor/local_endpoint/overload2.html
/home/amir/boost_1_69_0/doc/html/boost_asio/reference/basic_socket_acceptor/local_endpoint/overload1.html
/home/amir/boost_1_69_0/doc/html/boost_asio/reference/basic_socket_acceptor/keep_alive.html
/home/amir/boost_1_69_0/doc/html/boost_asio/reference/basic_socket_acceptor/async_wait.html
/home/amir/boost_1_69_0/doc/html/boost_asio/reference/basic_socket_acceptor/basic_socket_acceptor.html
/home/amir/boost_1_69_0/doc/html/boost_asio/reference/basic_socket_acceptor/out_of_band_inline.html
/home/amir/boost_1_69_0/doc/html/boost_asio/reference/basic_socket_acceptor/basic_socket_acceptor/overload2.html
/home/amir/boost_1_69_0/doc/html/boost_asio/reference/basic_socket_acceptor/basic_socket_acceptor/overload4.html
/home/amir/boost_1_69_0/doc/html/boost_asio/reference/basic_socket_acceptor/basic_socket_acceptor/overload3.html
/home/amir/boost_1_69_0/doc/html/boost_asio/reference/basic_socket_acceptor/basic_socket_acceptor/overload1.html
/home/amir/boost_1_69_0/doc/html/boost_asio/reference/basic_socket_acceptor/async_accept.html
/home/amir/boost_1_69_0/doc/html/boost_asio/reference/basic_socket_acceptor/reuse_address.html
/home/amir/boost_1_69_0/doc/html/boost_asio/reference/basic_socket_acceptor/open/overload2.html
/home/amir/boost_1_69_0/doc/html/boost_asio/reference/basic_socket_acceptor/open/overload1.html
/home/amir/boost_1_69_0/doc/html/boost_asio/reference/basic_socket_acceptor/linger.html
/home/amir/boost_1_69_0/doc/html/boost_asio/reference/basic_socket_acceptor/get_io_service.html
/home/amir/boost_1_69_0/doc/html/boost_asio/reference/basic_socket_acceptor/bytes_readable.html
/home/amir/boost_1_69_0/doc/html/boost_asio/reference/basic_socket_acceptor/enable_connection_aborted.html
/home/amir/boost_1_69_0/doc/html/boost_asio/reference/basic_socket_acceptor/broadcast.html
/home/amir/boost_1_69_0/doc/html/boost_asio/reference/basic_socket_acceptor/accept/overload2.html
/home/amir/boost_1_69_0/doc/html/boost_asio/reference/basic_socket_acceptor/accept/overload9.html
/home/amir/boost_1_69_0/doc/html/boost_asio/reference/basic_socket_acceptor/accept/overload4.html
/home/amir/boost_1_69_0/doc/html/boost_asio/reference/basic_socket_acceptor/accept/overload7.html
/home/amir/boost_1_69_0/doc/html/boost_asio/reference/basic_socket_acceptor/accept/overload5.html
/home/amir/boost_1_69_0/doc/html/boost_asio/reference/basic_socket_acceptor/accept/overload3.html
/home/amir/boost_1_69_0/doc/html/boost_asio/reference/basic_socket_acceptor/accept/overload11.html
/home/amir/boost_1_69_0/doc/html/boost_asio/reference/basic_socket_acceptor/accept/overload1.html
/home/amir/boost_1_69_0/doc/html/boost_asio/reference/basic_socket_acceptor/accept/overload6.html
/home/amir/boost_1_69_0/doc/html/boost_asio/reference/basic_socket_acceptor/accept/overload8.html
/home/amir/boost_1_69_0/doc/html/boost_asio/reference/basic_socket_acceptor/accept/overload10.html
/home/amir/boost_1_69_0/doc/html/boost_asio/reference/basic_socket_acceptor/accept/overload12.html
/home/amir/boost_1_69_0/doc/html/boost_asio/reference/basic_socket_acceptor/receive_low_watermark.html
/home/amir/boost_1_69_0/doc/html/boost_asio/reference/buffer_sequence_end.html
/home/amir/boost_1_69_0/doc/html/boost_asio/reference/system_timer.html
/home/amir/boost_1_69_0/doc/html/boost_asio/reference/basic_deadline_timer.html
/home/amir/boost_1_69_0/doc/html/boost_asio/reference/posix__descriptor_base/bytes_readable.html
/home/amir/boost_1_69_0/doc/html/boost_asio/reference/ssl__error__stream_category.html
/home/amir/boost_1_69_0/doc/html/boost_asio/reference/is_error_code_enum_lt__basic_errors__gt_/value.html
/home/amir/boost_1_69_0/doc/html/boost_asio/reference/Handler.html
/home/amir/boost_1_69_0/doc/html/boost_asio/reference/ShutdownHandler.html
/home/amir/boost_1_69_0/doc/html/boost_asio/reference/MoveAcceptHandler.html
/home/amir/boost_1_69_0/doc/html/boost_asio/reference/windows__random_access_handle/close/overload2.html
/home/amir/boost_1_69_0/doc/html/boost_asio/reference/windows__random_access_handle/close/overload1.html
/home/amir/boost_1_69_0/doc/html/boost_asio/reference/windows__random_access_handle/async_read_some_at.html
/home/amir/boost_1_69_0/doc/html/boost_asio/reference/windows__random_access_handle/get_io_context.html
/home/amir/boost_1_69_0/doc/html/boost_asio/reference/windows__random_access_handle/cancel/overload2.html
/home/amir/boost_1_69_0/doc/html/boost_asio/reference/windows__random_access_handle/cancel/overload1.html
/home/amir/boost_1_69_0/doc/html/boost_asio/reference/windows__random_access_handle/async_write_some_at.html
/home/amir/boost_1_69_0/doc/html/boost_asio/reference/windows__random_access_handle/write_some_at/overload1.html
/home/amir/boost_1_69_0/doc/html/boost_asio/reference/windows__random_access_handle/get_io_service.html
/home/amir/boost_1_69_0/doc/html/boost_asio/reference/windows__random_access_handle/read_some_at/overload1.html
/home/amir/boost_1_69_0/doc/html/boost_asio/reference/windows__random_access_handle/random_access_handle.html
/home/amir/boost_1_69_0/doc/html/boost_asio/reference/windows__random_access_handle/random_access_handle/overload2.html
/home/amir/boost_1_69_0/doc/html/boost_asio/reference/windows__random_access_handle/random_access_handle/overload1.html
/home/amir/boost_1_69_0/doc/html/boost_asio/reference/basic_io_object/get_io_context.html
/home/amir/boost_1_69_0/doc/html/boost_asio/reference/basic_io_object/basic_io_object.html
/home/amir/boost_1_69_0/doc/html/boost_asio/reference/basic_io_object/basic_io_object/overload1.html
/home/amir/boost_1_69_0/doc/html/boost_asio/reference/basic_io_object/executor_type.html
/home/amir/boost_1_69_0/doc/html/boost_asio/reference/basic_io_object/get_io_service.html
/home/amir/boost_1_69_0/doc/html/boost_asio/reference/streambuf.html
/home/amir/boost_1_69_0/doc/html/boost_asio/reference/system_context/make_service.html
/home/amir/boost_1_69_0/doc/html/boost_asio/reference/system_context/add_service.html
/home/amir/boost_1_69_0/doc/html/boost_asio/reference/basic_socket_streambuf/expires_from_now/overload2.html
/home/amir/boost_1_69_0/doc/html/boost_asio/reference/basic_socket_streambuf/expires_after.html
/home/amir/boost_1_69_0/doc/html/boost_asio/reference/basic_socket_streambuf/expires_at/overload2.html
/home/amir/boost_1_69_0/doc/html/boost_asio/reference/io_context.html
/home/amir/boost_1_69_0/doc/html/boost_asio/reference/placeholders__bytes_transferred.html
/home/amir/boost_1_69_0/doc/html/boost_asio/reference/basic_streambuf.html
/home/amir/boost_1_69_0/doc/html/boost_asio/reference/generic__stream_protocol.html
/home/amir/boost_1_69_0/doc/html/boost_asio/reference/RangeConnectHandler.html
/home/amir/boost_1_69_0/doc/html/boost_asio/reference/const_buffer.html
/home/amir/boost_1_69_0/doc/html/boost_asio/reference/windows__overlapped_ptr/overlapped_ptr/overload2.html
/home/amir/boost_1_69_0/doc/html/boost_asio/reference/windows__overlapped_ptr/reset.html
/home/amir/boost_1_69_0/doc/html/boost_asio/reference/windows__overlapped_ptr/reset/overload2.html
/home/amir/boost_1_69_0/doc/html/boost_asio/reference/windows__overlapped_ptr/overlapped_ptr.html
/home/amir/boost_1_69_0/doc/html/boost_asio/reference/io_context__strand.html
/home/amir/boost_1_69_0/doc/html/boost_asio/reference/io_context/make_service.html
/home/amir/boost_1_69_0/doc/html/boost_asio/reference/io_context/add_service.html
/home/amir/boost_1_69_0/doc/html/boost_asio/reference/signal_set/get_io_context.html
/home/amir/boost_1_69_0/doc/html/boost_asio/reference/signal_set/cancel/overload2.html
/home/amir/boost_1_69_0/doc/html/boost_asio/reference/signal_set/cancel/overload1.html
/home/amir/boost_1_69_0/doc/html/boost_asio/reference/signal_set/signal_set.html
/home/amir/boost_1_69_0/doc/html/boost_asio/reference/signal_set/async_wait.html
/home/amir/boost_1_69_0/doc/html/boost_asio/reference/signal_set/get_io_service.html
/home/amir/boost_1_69_0/doc/html/boost_asio/reference/signal_set/signal_set/overload2.html
/home/amir/boost_1_69_0/doc/html/boost_asio/reference/signal_set/signal_set/overload4.html
/home/amir/boost_1_69_0/doc/html/boost_asio/reference/signal_set/signal_set/overload3.html
/home/amir/boost_1_69_0/doc/html/boost_asio/reference/signal_set/signal_set/overload1.html
/home/amir/boost_1_69_0/doc/html/boost_asio/reference/ip__tcp/acceptor.html
/home/amir/boost_1_69_0/doc/html/boost_asio/reference/ip__tcp/no_delay.html
/home/amir/boost_1_69_0/doc/html/boost_asio/reference/read_until.html
/home/amir/boost_1_69_0/doc/html/boost_asio/reference/ip__basic_resolver/async_resolve/overload2.html
/home/amir/boost_1_69_0/doc/html/boost_asio/reference/ip__basic_resolver/async_resolve/overload4.html
/home/amir/boost_1_69_0/doc/html/boost_asio/reference/ip__basic_resolver/async_resolve/overload5.html
/home/amir/boost_1_69_0/doc/html/boost_asio/reference/ip__basic_resolver/async_resolve/overload3.html
/home/amir/boost_1_69_0/doc/html/boost_asio/reference/ip__basic_resolver/async_resolve/overload1.html
/home/amir/boost_1_69_0/doc/html/boost_asio/reference/ip__basic_resolver/async_resolve/overload6.html
/home/amir/boost_1_69_0/doc/html/boost_asio/reference/ip__basic_resolver/get_io_context.html
/home/amir/boost_1_69_0/doc/html/boost_asio/reference/ip__basic_resolver/basic_resolver.html
/home/amir/boost_1_69_0/doc/html/boost_asio/reference/ip__basic_resolver/basic_resolver/overload1.html
/home/amir/boost_1_69_0/doc/html/boost_asio/reference/ip__basic_resolver/get_io_service.html
/home/amir/boost_1_69_0/doc/html/boost_asio/reference/ip__basic_resolver/cancel.html
/home/amir/boost_1_69_0/doc/html/boost_asio/reference/placeholders__endpoint.html
/home/amir/boost_1_69_0/doc/html/boost_asio/reference/use_future_t.html
/home/amir/boost_1_69_0/doc/html/boost_asio/reference/is_error_code_enum_lt__boost__asio__ssl__error__stream_errors__gt_/value.html
/home/amir/boost_1_69_0/doc/html/boost_asio/reference/is_error_code_enum_lt__boost__asio__ssl__error__stream_errors__gt_.html
/home/amir/boost_1_69_0/doc/html/boost_asio/reference/placeholders__results.html
/home/amir/boost_1_69_0/doc/html/boost_asio/reference/add_service.html
/home/amir/boost_1_69_0/doc/html/boost_asio/reference/basic_raw_socket/set_option/overload2.html
/home/amir/boost_1_69_0/doc/html/boost_asio/reference/basic_raw_socket/set_option/overload1.html
/home/amir/boost_1_69_0/doc/html/boost_asio/reference/basic_raw_socket/close/overload2.html
/home/amir/boost_1_69_0/doc/html/boost_asio/reference/basic_raw_socket/close/overload1.html
/home/amir/boost_1_69_0/doc/html/boost_asio/reference/basic_raw_socket/async_receive/overload2.html
/home/amir/boost_1_69_0/doc/html/boost_asio/reference/basic_raw_socket/async_receive/overload1.html
/home/amir/boost_1_69_0/doc/html/boost_asio/reference/basic_raw_socket/debug.html
/home/amir/boost_1_69_0/doc/html/boost_asio/reference/basic_raw_socket/get_option/overload2.html
/home/amir/boost_1_69_0/doc/html/boost_asio/reference/basic_raw_socket/get_option/overload1.html
/home/amir/boost_1_69_0/doc/html/boost_asio/reference/basic_raw_socket/receive/overload1.html
/home/amir/boost_1_69_0/doc/html/boost_asio/reference/basic_raw_socket/send_to/overload1.html
/home/amir/boost_1_69_0/doc/html/boost_asio/reference/basic_raw_socket/shutdown/overload2.html
/home/amir/boost_1_69_0/doc/html/boost_asio/reference/basic_raw_socket/shutdown/overload1.html
/home/amir/boost_1_69_0/doc/html/boost_asio/reference/basic_raw_socket/basic_raw_socket.html
/home/amir/boost_1_69_0/doc/html/boost_asio/reference/basic_raw_socket/receive_buffer_size.html
/home/amir/boost_1_69_0/doc/html/boost_asio/reference/basic_raw_socket/send_buffer_size.html
/home/amir/boost_1_69_0/doc/html/boost_asio/reference/basic_raw_socket/native_non_blocking/overload2.html
/home/amir/boost_1_69_0/doc/html/boost_asio/reference/basic_raw_socket/native_non_blocking/overload3.html
/home/amir/boost_1_69_0/doc/html/boost_asio/reference/basic_raw_socket/native_non_blocking/overload1.html
/home/amir/boost_1_69_0/doc/html/boost_asio/reference/basic_raw_socket/release/overload2.html
/home/amir/boost_1_69_0/doc/html/boost_asio/reference/basic_raw_socket/release/overload1.html
/home/amir/boost_1_69_0/doc/html/boost_asio/reference/basic_raw_socket/send_low_watermark.html
/home/amir/boost_1_69_0/doc/html/boost_asio/reference/basic_raw_socket/bind/overload2.html
/home/amir/boost_1_69_0/doc/html/boost_asio/reference/basic_raw_socket/bind/overload1.html
/home/amir/boost_1_69_0/doc/html/boost_asio/reference/basic_raw_socket/get_io_context.html
/home/amir/boost_1_69_0/doc/html/boost_asio/reference/basic_raw_socket/connect/overload2.html
/home/amir/boost_1_69_0/doc/html/boost_asio/reference/basic_raw_socket/connect/overload1.html
/home/amir/boost_1_69_0/doc/html/boost_asio/reference/basic_raw_socket/cancel/overload2.html
/home/amir/boost_1_69_0/doc/html/boost_asio/reference/basic_raw_socket/cancel/overload1.html
/home/amir/boost_1_69_0/doc/html/boost_asio/reference/basic_raw_socket/async_receive_from/overload2.html
/home/amir/boost_1_69_0/doc/html/boost_asio/reference/basic_raw_socket/async_receive_from/overload1.html
/home/amir/boost_1_69_0/doc/html/boost_asio/reference/basic_raw_socket/io_control/overload2.html
/home/amir/boost_1_69_0/doc/html/boost_asio/reference/basic_raw_socket/io_control/overload1.html
/home/amir/boost_1_69_0/doc/html/boost_asio/reference/basic_raw_socket/non_blocking/overload2.html
/home/amir/boost_1_69_0/doc/html/boost_asio/reference/basic_raw_socket/non_blocking/overload3.html
/home/amir/boost_1_69_0/doc/html/boost_asio/reference/basic_raw_socket/non_blocking/overload1.html
/home/amir/boost_1_69_0/doc/html/boost_asio/reference/basic_raw_socket/do_not_route.html
/home/amir/boost_1_69_0/doc/html/boost_asio/reference/basic_raw_socket/receive_from/overload1.html
/home/amir/boost_1_69_0/doc/html/boost_asio/reference/basic_raw_socket/wait/overload2.html
/home/amir/boost_1_69_0/doc/html/boost_asio/reference/basic_raw_socket/wait/overload1.html
/home/amir/boost_1_69_0/doc/html/boost_asio/reference/basic_raw_socket/local_endpoint/overload2.html
/home/amir/boost_1_69_0/doc/html/boost_asio/reference/basic_raw_socket/local_endpoint/overload1.html
/home/amir/boost_1_69_0/doc/html/boost_asio/reference/basic_raw_socket/keep_alive.html
/home/amir/boost_1_69_0/doc/html/boost_asio/reference/basic_raw_socket/async_send_to/overload2.html
/home/amir/boost_1_69_0/doc/html/boost_asio/reference/basic_raw_socket/async_send_to/overload1.html
/home/amir/boost_1_69_0/doc/html/boost_asio/reference/basic_raw_socket/async_wait.html
/home/amir/boost_1_69_0/doc/html/boost_asio/reference/basic_raw_socket/out_of_band_inline.html
/home/amir/boost_1_69_0/doc/html/boost_asio/reference/basic_raw_socket/remote_endpoint/overload2.html
/home/amir/boost_1_69_0/doc/html/boost_asio/reference/basic_raw_socket/remote_endpoint/overload1.html
/home/amir/boost_1_69_0/doc/html/boost_asio/reference/basic_raw_socket/reuse_address.html
/home/amir/boost_1_69_0/doc/html/boost_asio/reference/basic_raw_socket/open/overload2.html
/home/amir/boost_1_69_0/doc/html/boost_asio/reference/basic_raw_socket/open/overload1.html
/home/amir/boost_1_69_0/doc/html/boost_asio/reference/basic_raw_socket/async_connect.html
/home/amir/boost_1_69_0/doc/html/boost_asio/reference/basic_raw_socket/linger.html
/home/amir/boost_1_69_0/doc/html/boost_asio/reference/basic_raw_socket/send/overload1.html
/home/amir/boost_1_69_0/doc/html/boost_asio/reference/basic_raw_socket/async_send/overload2.html
/home/amir/boost_1_69_0/doc/html/boost_asio/reference/basic_raw_socket/async_send/overload1.html
/home/amir/boost_1_69_0/doc/html/boost_asio/reference/basic_raw_socket/get_io_service.html
/home/amir/boost_1_69_0/doc/html/boost_asio/reference/basic_raw_socket/bytes_readable.html
/home/amir/boost_1_69_0/doc/html/boost_asio/reference/basic_raw_socket/enable_connection_aborted.html
/home/amir/boost_1_69_0/doc/html/boost_asio/reference/basic_raw_socket/broadcast.html
/home/amir/boost_1_69_0/doc/html/boost_asio/reference/basic_raw_socket/basic_raw_socket/overload2.html
/home/amir/boost_1_69_0/doc/html/boost_asio/reference/basic_raw_socket/basic_raw_socket/overload4.html
/home/amir/boost_1_69_0/doc/html/boost_asio/reference/basic_raw_socket/basic_raw_socket/overload3.html
/home/amir/boost_1_69_0/doc/html/boost_asio/reference/basic_raw_socket/basic_raw_socket/overload1.html
/home/amir/boost_1_69_0/doc/html/boost_asio/reference/basic_raw_socket/receive_low_watermark.html
/home/amir/boost_1_69_0/doc/html/boost_asio/reference/error__system_category.html
/home/amir/boost_1_69_0/doc/html/boost_asio/reference/IteratorConnectHandler.html
/home/amir/boost_1_69_0/doc/html/boost_asio/reference/high_resolution_timer.html
/home/amir/boost_1_69_0/doc/html/boost_asio/reference/transfer_exactly.html
/home/amir/boost_1_69_0/doc/html/boost_asio/reference/read_at/overload2.html
/home/amir/boost_1_69_0/doc/html/boost_asio/reference/read_at/overload5.html
/home/amir/boost_1_69_0/doc/html/boost_asio/reference/read_at/overload3.html
/home/amir/boost_1_69_0/doc/html/boost_asio/reference/read_at/overload1.html
/home/amir/boost_1_69_0/doc/html/boost_asio/reference/read_at/overload6.html
/home/amir/boost_1_69_0/doc/html/boost_asio/reference/is_error_code_enum_lt__misc_errors__gt_.html
/home/amir/boost_1_69_0/doc/html/boost_asio/reference/io_service.html
/home/amir/boost_1_69_0/doc/html/boost_asio/reference/error__ssl_category.html
/home/amir/boost_1_69_0/doc/html/boost_asio/reference/HandshakeHandler.html
/home/amir/boost_1_69_0/doc/html/boost_asio/reference/is_error_code_enum_lt__misc_errors__gt_/value.html
/home/amir/boost_1_69_0/doc/html/boost_asio/reference/experimental__detached_t.html
/home/amir/boost_1_69_0/doc/html/boost_asio/reference/basic_streambuf_ref/const_buffers_type.html
/home/amir/boost_1_69_0/doc/html/boost_asio/reference/basic_streambuf_ref/mutable_buffers_type.html
/home/amir/boost_1_69_0/doc/html/process/reference.html
/home/amir/boost_1_69_0/doc/html/boost/process/spawn.html
/home/amir/boost_1_69_0/doc/html/boost/process/on_exit.html
/home/amir/boost_1_69_0/doc/html/boost/process/std_in.html
/home/amir/boost_1_69_0/doc/html/boost/process/std_out.html
/home/amir/boost_1_69_0/doc/html/boost/process/async_pipe.html
/home/amir/boost_1_69_0/doc/html/boost_process/tutorial.html
/home/amir/boost_1_69_0/doc/html/boost_process/extend.html
/home/amir/boost_1_69_0/libs/log/doc/tmp/sinks_reference.xml
/home/amir/boost_1_69_0/libs/log/src/syslog_backend.cpp
/home/amir/boost_1_69_0/libs/coroutine/doc/coro.qbk
/home/amir/boost_1_69_0/libs/coroutine/doc/html/coroutine/motivation.html
/home/amir/boost_1_69_0/libs/coroutine/doc/motivation.qbk
/home/amir/boost_1_69_0/libs/process/test/bind_stderr.cpp
/home/amir/boost_1_69_0/libs/process/test/async_system_fail.cpp
/home/amir/boost_1_69_0/libs/process/test/async_system_stackless.cpp
/home/amir/boost_1_69_0/libs/process/test/bind_stdout_stderr.cpp
/home/amir/boost_1_69_0/libs/process/test/on_exit.cpp
/home/amir/boost_1_69_0/libs/process/test/async_system_stackful_except.cpp
/home/amir/boost_1_69_0/libs/process/test/wait.cpp
/home/amir/boost_1_69_0/libs/process/test/async_system_stackful_error.cpp
/home/amir/boost_1_69_0/libs/process/test/async_system_stackful.cpp
/home/amir/boost_1_69_0/libs/process/test/on_exit3.cpp
/home/amir/boost_1_69_0/libs/process/test/async.cpp
/home/amir/boost_1_69_0/libs/process/test/system_test1.cpp
/home/amir/boost_1_69_0/libs/process/test/exit_code.cpp
/home/amir/boost_1_69_0/libs/process/test/on_exit2.cpp
/home/amir/boost_1_69_0/libs/process/test/spawn_fail.cpp
/home/amir/boost_1_69_0/libs/process/test/bind_stdout.cpp
/home/amir/boost_1_69_0/libs/process/test/async_fut.cpp
/home/amir/boost_1_69_0/libs/process/test/system_test2.cpp
/home/amir/boost_1_69_0/libs/process/test/async_system_future.cpp
/home/amir/boost_1_69_0/libs/process/test/bind_stdin.cpp
/home/amir/boost_1_69_0/libs/process/test/async_pipe.cpp
/home/amir/boost_1_69_0/libs/process/test/spawn.cpp
/home/amir/boost_1_69_0/libs/process/doc/extend.qbk
/home/amir/boost_1_69_0/libs/process/doc/autodoc.xml
/home/amir/boost_1_69_0/libs/process/doc/tutorial.qbk
/home/amir/boost_1_69_0/libs/process/example/wait.cpp
/home/amir/boost_1_69_0/libs/process/example/io.cpp
/home/amir/boost_1_69_0/libs/process/example/async_io.cpp
/home/amir/boost_1_69_0/libs/thread/test/test_9303.cpp
/home/amir/boost_1_69_0/libs/fiber/examples/asio/ps/publisher.cpp
/home/amir/boost_1_69_0/libs/fiber/examples/asio/ps/server.cpp
/home/amir/boost_1_69_0/libs/fiber/examples/asio/ps/subscriber.cpp
/home/amir/boost_1_69_0/libs/fiber/examples/asio/autoecho.cpp
/home/amir/boost_1_69_0/libs/fiber/examples/asio/exchange.cpp
/home/amir/boost_1_69_0/libs/fiber/examples/asio/round_robin.hpp
/home/amir/boost_1_69_0/libs/fiber/doc/asio.qbk
/home/amir/boost_1_69_0/libs/fiber/doc/callbacks.qbk
/home/amir/boost_1_69_0/libs/fiber/doc/integration.qbk
/home/amir/boost_1_69_0/libs/fiber/doc/fibers.qbk
/home/amir/boost_1_69_0/libs/phoenix/example/adapted_echo_server.cpp
/home/amir/boost_1_69_0/libs/beast/test/extras/include/boost/beast/test/sig_wait.hpp
/home/amir/boost_1_69_0/libs/beast/test/extras/include/boost/beast/test/websocket.hpp
/home/amir/boost_1_69_0/libs/beast/test/extras/include/boost/beast/test/yield_to.hpp
/home/amir/boost_1_69_0/libs/beast/test/doc/core_snippets.cpp
/home/amir/boost_1_69_0/libs/beast/test/doc/exemplars.cpp
/home/amir/boost_1_69_0/libs/beast/test/doc/http_snippets.cpp
/home/amir/boost_1_69_0/libs/beast/test/doc/core_examples.cpp
/home/amir/boost_1_69_0/libs/beast/test/doc/websocket_snippets.cpp
/home/amir/boost_1_69_0/libs/beast/test/doc/http_examples.cpp
/home/amir/boost_1_69_0/libs/beast/test/bench/wsload/wsload.cpp
/home/amir/boost_1_69_0/libs/beast/test/bench/buffers/bench_buffers.cpp
/home/amir/boost_1_69_0/libs/beast/test/bench/parser/bench_parser.cpp
/home/amir/boost_1_69_0/libs/beast/test/bench/parser/nodejs_parser.hpp
/home/amir/boost_1_69_0/libs/beast/test/beast/core/flat_static_buffer.cpp
/home/amir/boost_1_69_0/libs/beast/test/beast/core/static_buffer.cpp
/home/amir/boost_1_69_0/libs/beast/test/beast/core/buffers_suffix.cpp
/home/amir/boost_1_69_0/libs/beast/test/beast/core/type_traits.cpp
/home/amir/boost_1_69_0/libs/beast/test/beast/core/buffer.cpp
/home/amir/boost_1_69_0/libs/beast/test/beast/core/buffered_read_stream.cpp
/home/amir/boost_1_69_0/libs/beast/test/beast/core/buffers_adapter.cpp
/home/amir/boost_1_69_0/libs/beast/test/beast/core/buffers_prefix.cpp
/home/amir/boost_1_69_0/libs/beast/test/beast/core/flat_buffer.cpp
/home/amir/boost_1_69_0/libs/beast/test/beast/core/bind_handler.cpp
/home/amir/boost_1_69_0/libs/beast/test/beast/core/buffers_cat.cpp
/home/amir/boost_1_69_0/libs/beast/test/beast/core/read_size.cpp
/home/amir/boost_1_69_0/libs/beast/test/beast/core/buffer_test.hpp
/home/amir/boost_1_69_0/libs/beast/test/beast/core/multi_buffer.cpp
/home/amir/boost_1_69_0/libs/beast/test/beast/websocket/write.cpp
/home/amir/boost_1_69_0/libs/beast/test/beast/websocket/read1.cpp
/home/amir/boost_1_69_0/libs/beast/test/beast/websocket/ping.cpp
/home/amir/boost_1_69_0/libs/beast/test/beast/websocket/utf8_checker.cpp
/home/amir/boost_1_69_0/libs/beast/test/beast/websocket/accept.cpp
/home/amir/boost_1_69_0/libs/beast/test/beast/websocket/read2.cpp
/home/amir/boost_1_69_0/libs/beast/test/beast/websocket/close.cpp
/home/amir/boost_1_69_0/libs/beast/test/beast/websocket/test.hpp
/home/amir/boost_1_69_0/libs/beast/test/beast/websocket/doc_snippets.cpp
/home/amir/boost_1_69_0/libs/beast/test/beast/websocket/stream.cpp
/home/amir/boost_1_69_0/libs/beast/test/beast/websocket/handshake.cpp
/home/amir/boost_1_69_0/libs/beast/test/beast/http/write.cpp
/home/amir/boost_1_69_0/libs/beast/test/beast/http/test_parser.hpp
/home/amir/boost_1_69_0/libs/beast/test/beast/http/message_fuzz.hpp
/home/amir/boost_1_69_0/libs/beast/test/beast/http/serializer.cpp
/home/amir/boost_1_69_0/libs/beast/test/beast/http/span_body.cpp
/home/amir/boost_1_69_0/libs/beast/test/beast/http/basic_parser.cpp
/home/amir/boost_1_69_0/libs/beast/test/beast/http/file_body.cpp
/home/amir/boost_1_69_0/libs/beast/test/beast/http/dynamic_body.cpp
/home/amir/boost_1_69_0/libs/beast/test/beast/http/read.cpp
/home/amir/boost_1_69_0/libs/beast/test/beast/http/parser.cpp
/home/amir/boost_1_69_0/libs/beast/test/beast/http/chunk_encode.cpp
/home/amir/boost_1_69_0/libs/beast/test/beast/experimental/icy_stream.cpp
/home/amir/boost_1_69_0/libs/beast/test/beast/experimental/flat_stream.cpp
/home/amir/boost_1_69_0/libs/beast/test/beast/experimental/timeout_socket.cpp
/home/amir/boost_1_69_0/libs/beast/test/beast/experimental/timeout_service.cpp
/home/amir/boost_1_69_0/libs/beast/doc/docca/include/docca/doxygen.xsl
/home/amir/boost_1_69_0/libs/beast/doc/qbk/03_core/1_asio.qbk
/home/amir/boost_1_69_0/libs/beast/doc/qbk/reference.qbk
/home/amir/boost_1_69_0/libs/beast/doc/qbk/08_design/3_websocket_zaphoyd.qbk
/home/amir/boost_1_69_0/libs/beast/doc/qbk/08_design/4_faq.qbk
/home/amir/boost_1_69_0/libs/beast/doc/qbk/00_main.qbk
/home/amir/boost_1_69_0/libs/beast/doc/qbk/07_concepts/DynamicBuffer.qbk
/home/amir/boost_1_69_0/libs/beast/doc/qbk/07_concepts/Streams.qbk
/home/amir/boost_1_69_0/libs/beast/doc/html/beast/more_examples/expect_100_continue_server.html
/home/amir/boost_1_69_0/libs/beast/doc/html/beast/using_io/example_detect_ssl.html
/home/amir/boost_1_69_0/libs/beast/doc/html/beast/using_io/writing_composed_operations.html
/home/amir/boost_1_69_0/libs/beast/doc/html/beast/ref/boost__beast__http__error.html
/home/amir/boost_1_69_0/libs/beast/doc/html/beast/ref/boost__beast__websocket__async_teardown/overload2.html
/home/amir/boost_1_69_0/libs/beast/doc/html/beast/ref/boost__beast__websocket__async_teardown/overload3.html
/home/amir/boost_1_69_0/libs/beast/doc/html/beast/ref/boost__beast__websocket__async_teardown/overload1.html
/home/amir/boost_1_69_0/libs/beast/doc/html/beast/ref/boost__beast__basic_timeout_socket/async_read_some.html
/home/amir/boost_1_69_0/libs/beast/doc/html/beast/ref/boost__beast__basic_timeout_socket/async_write_some.html
/home/amir/boost_1_69_0/libs/beast/example/echo-op/echo_op.cpp
/home/amir/boost_1_69_0/libs/beast/example/cppcon2018/net.hpp
/home/amir/boost_1_69_0/libs/beast/example/websocket/client/async/websocket_client_async.cpp
/home/amir/boost_1_69_0/libs/beast/example/websocket/client/sync-ssl/websocket_client_sync_ssl.cpp
/home/amir/boost_1_69_0/libs/beast/example/websocket/client/sync/websocket_client_sync.cpp
/home/amir/boost_1_69_0/libs/beast/example/websocket/client/async-ssl/websocket_client_async_ssl.cpp
/home/amir/boost_1_69_0/libs/beast/example/websocket/client/coro-ssl/websocket_client_coro_ssl.cpp
/home/amir/boost_1_69_0/libs/beast/example/websocket/client/coro/websocket_client_coro.cpp
/home/amir/boost_1_69_0/libs/beast/example/websocket/server/async/websocket_server_async.cpp
/home/amir/boost_1_69_0/libs/beast/example/websocket/server/stackless/websocket_server_stackless.cpp
/home/amir/boost_1_69_0/libs/beast/example/websocket/server/sync-ssl/websocket_server_sync_ssl.cpp
/home/amir/boost_1_69_0/libs/beast/example/websocket/server/stackless-ssl/websocket_server_stackless_ssl.cpp
/home/amir/boost_1_69_0/libs/beast/example/websocket/server/sync/websocket_server_sync.cpp
/home/amir/boost_1_69_0/libs/beast/example/websocket/server/async-ssl/websocket_server_async_ssl.cpp
/home/amir/boost_1_69_0/libs/beast/example/websocket/server/fast/websocket_server_fast.cpp
/home/amir/boost_1_69_0/libs/beast/example/websocket/server/coro-ssl/websocket_server_coro_ssl.cpp
/home/amir/boost_1_69_0/libs/beast/example/websocket/server/coro/websocket_server_coro.cpp
/home/amir/boost_1_69_0/libs/beast/example/advanced/server-flex/advanced_server_flex.cpp
/home/amir/boost_1_69_0/libs/beast/example/advanced/server/advanced_server.cpp
/home/amir/boost_1_69_0/libs/beast/example/doc/http_examples.hpp
/home/amir/boost_1_69_0/libs/beast/example/http/client/async/http_client_async.cpp
/home/amir/boost_1_69_0/libs/beast/example/http/client/sync-ssl/http_client_sync_ssl.cpp
/home/amir/boost_1_69_0/libs/beast/example/http/client/sync/http_client_sync.cpp
/home/amir/boost_1_69_0/libs/beast/example/http/client/crawl/http_crawl.cpp
/home/amir/boost_1_69_0/libs/beast/example/http/client/async-ssl/http_client_async_ssl.cpp
/home/amir/boost_1_69_0/libs/beast/example/http/client/coro-ssl/http_client_coro_ssl.cpp
/home/amir/boost_1_69_0/libs/beast/example/http/client/coro/http_client_coro.cpp
/home/amir/boost_1_69_0/libs/beast/example/http/server/async/http_server_async.cpp
/home/amir/boost_1_69_0/libs/beast/example/http/server/stackless/http_server_stackless.cpp
/home/amir/boost_1_69_0/libs/beast/example/http/server/sync-ssl/http_server_sync_ssl.cpp
/home/amir/boost_1_69_0/libs/beast/example/http/server/stackless-ssl/http_server_stackless_ssl.cpp
/home/amir/boost_1_69_0/libs/beast/example/http/server/sync/http_server_sync.cpp
/home/amir/boost_1_69_0/libs/beast/example/http/server/flex/http_server_flex.cpp
/home/amir/boost_1_69_0/libs/beast/example/http/server/async-ssl/http_server_async_ssl.cpp
/home/amir/boost_1_69_0/libs/beast/example/http/server/fast/http_server_fast.cpp
/home/amir/boost_1_69_0/libs/beast/example/http/server/coro-ssl/http_server_coro_ssl.cpp
/home/amir/boost_1_69_0/libs/beast/example/http/server/coro/http_server_coro.cpp
/home/amir/boost_1_69_0/libs/beast/example/http/server/small/http_server_small.cpp
/home/amir/boost_1_69_0/libs/beast/example/common/session_alloc.hpp
/home/amir/boost_1_69_0/libs/beast/example/common/root_certificates.hpp
/home/amir/boost_1_69_0/libs/beast/example/common/detect_ssl.hpp
/home/amir/boost_1_69_0/libs/beast/example/common/server_certificate.hpp
/home/amir/boost_1_69_0/libs/beast/CHANGELOG.md
/home/amir/boost_1_69_0/libs/coroutine2/doc/coro.qbk
/home/amir/boost_1_69_0/libs/coroutine2/doc/motivation.qbk
/home/amir/boost_1_69_0/libs/asio/test/write.cpp
/home/amir/boost_1_69_0/libs/asio/test/archetypes/async_ops.hpp
/home/amir/boost_1_69_0/libs/asio/test/archetypes/deprecated_async_ops.hpp
/home/amir/boost_1_69_0/libs/asio/test/streambuf.cpp
/home/amir/boost_1_69_0/libs/asio/test/use_future.cpp
/home/amir/boost_1_69_0/libs/asio/test/error.cpp
/home/amir/boost_1_69_0/libs/asio/test/is_write_buffered.cpp
/home/amir/boost_1_69_0/libs/asio/test/is_read_buffered.cpp
/home/amir/boost_1_69_0/libs/asio/test/unit_test.hpp
/home/amir/boost_1_69_0/libs/asio/test/socket_base.cpp
/home/amir/boost_1_69_0/libs/asio/test/buffered_write_stream.cpp
/home/amir/boost_1_69_0/libs/asio/test/local/datagram_protocol.cpp
/home/amir/boost_1_69_0/libs/asio/test/local/connect_pair.cpp
/home/amir/boost_1_69_0/libs/asio/test/local/stream_protocol.cpp
/home/amir/boost_1_69_0/libs/asio/test/generic/datagram_protocol.cpp
/home/amir/boost_1_69_0/libs/asio/test/generic/seq_packet_protocol.cpp
/home/amir/boost_1_69_0/libs/asio/test/generic/stream_protocol.cpp
/home/amir/boost_1_69_0/libs/asio/test/generic/raw_protocol.cpp
/home/amir/boost_1_69_0/libs/asio/test/buffer.cpp
/home/amir/boost_1_69_0/libs/asio/test/buffered_read_stream.cpp
/home/amir/boost_1_69_0/libs/asio/test/coroutine.cpp
/home/amir/boost_1_69_0/libs/asio/test/read_at.cpp
/home/amir/boost_1_69_0/libs/asio/test/buffers_iterator.cpp
/home/amir/boost_1_69_0/libs/asio/test/serial_port_base.cpp
/home/amir/boost_1_69_0/libs/asio/test/write_at.cpp
/home/amir/boost_1_69_0/libs/asio/test/windows/object_handle.cpp
/home/amir/boost_1_69_0/libs/asio/test/windows/overlapped_ptr.cpp
/home/amir/boost_1_69_0/libs/asio/test/windows/random_access_handle.cpp
/home/amir/boost_1_69_0/libs/asio/test/windows/stream_handle.cpp
/home/amir/boost_1_69_0/libs/asio/test/buffered_stream.cpp
/home/amir/boost_1_69_0/libs/asio/test/deadline_timer.cpp
/home/amir/boost_1_69_0/libs/asio/test/read.cpp
/home/amir/boost_1_69_0/libs/asio/test/ssl/stream.cpp
/home/amir/boost_1_69_0/libs/asio/test/read_until.cpp
/home/amir/boost_1_69_0/libs/asio/test/system_timer.cpp
/home/amir/boost_1_69_0/libs/asio/test/io_context.cpp
/home/amir/boost_1_69_0/libs/asio/test/ip/multicast.cpp
/home/amir/boost_1_69_0/libs/asio/test/ip/network_v4.cpp
/home/amir/boost_1_69_0/libs/asio/test/ip/tcp.cpp
/home/amir/boost_1_69_0/libs/asio/test/ip/address_v4.cpp
/home/amir/boost_1_69_0/libs/asio/test/ip/address.cpp
/home/amir/boost_1_69_0/libs/asio/test/ip/v6_only.cpp
/home/amir/boost_1_69_0/libs/asio/test/ip/address_v6.cpp
/home/amir/boost_1_69_0/libs/asio/test/ip/unicast.cpp
/home/amir/boost_1_69_0/libs/asio/test/ip/udp.cpp
/home/amir/boost_1_69_0/libs/asio/test/ip/icmp.cpp
/home/amir/boost_1_69_0/libs/asio/test/ip/host_name.cpp
/home/amir/boost_1_69_0/libs/asio/test/ip/network_v6.cpp
/home/amir/boost_1_69_0/libs/asio/test/serial_port.cpp
/home/amir/boost_1_69_0/libs/asio/test/strand.cpp
/home/amir/boost_1_69_0/libs/asio/test/latency/udp_server.cpp
/home/amir/boost_1_69_0/libs/asio/test/latency/udp_client.cpp
/home/amir/boost_1_69_0/libs/asio/test/latency/tcp_client.cpp
/home/amir/boost_1_69_0/libs/asio/test/latency/tcp_server.cpp
/home/amir/boost_1_69_0/libs/asio/test/posix/stream_descriptor.cpp
/home/amir/boost_1_69_0/libs/asio/test/signal_set.cpp
/home/amir/boost_1_69_0/libs/asio/test/connect.cpp
/home/amir/boost_1_69_0/libs/asio/doc/reference.qbk
/home/amir/boost_1_69_0/libs/asio/doc/reference.xsl
/home/amir/boost_1_69_0/libs/asio/doc/overview/other_protocols.qbk
/home/amir/boost_1_69_0/libs/asio/doc/overview/strands.qbk
/home/amir/boost_1_69_0/libs/asio/doc/overview/protocols.qbk
/home/amir/boost_1_69_0/libs/asio/doc/overview/allocation.qbk
/home/amir/boost_1_69_0/libs/asio/doc/overview/line_based.qbk
/home/amir/boost_1_69_0/libs/asio/doc/overview/buffers.qbk
/home/amir/boost_1_69_0/libs/asio/doc/overview/signals.qbk
/home/amir/boost_1_69_0/libs/asio/doc/overview/ssl.qbk
/home/amir/boost_1_69_0/libs/asio/doc/overview/spawn.qbk
/home/amir/boost_1_69_0/libs/asio/doc/overview/coroutines_ts.qbk
/home/amir/boost_1_69_0/libs/asio/doc/overview/coroutine.qbk
/home/amir/boost_1_69_0/libs/asio/doc/overview/posix.qbk
/home/amir/boost_1_69_0/libs/asio/doc/overview/cpp2011.qbk
/home/amir/boost_1_69_0/libs/asio/doc/overview/basics.qbk
/home/amir/boost_1_69_0/libs/asio/doc/requirements/ReadHandler.qbk
/home/amir/boost_1_69_0/libs/asio/doc/requirements/RangeConnectHandler.qbk
/home/amir/boost_1_69_0/libs/asio/doc/requirements/HandshakeHandler.qbk
/home/amir/boost_1_69_0/libs/asio/doc/requirements/ConnectHandler.qbk
/home/amir/boost_1_69_0/libs/asio/doc/requirements/MoveAcceptHandler.qbk
/home/amir/boost_1_69_0/libs/asio/doc/requirements/SignalHandler.qbk
/home/amir/boost_1_69_0/libs/asio/doc/requirements/AcceptHandler.qbk
/home/amir/boost_1_69_0/libs/asio/doc/requirements/IteratorConnectHandler.qbk
/home/amir/boost_1_69_0/libs/asio/doc/requirements/ResolveHandler.qbk
/home/amir/boost_1_69_0/libs/asio/doc/requirements/MutableBufferSequence.qbk
/home/amir/boost_1_69_0/libs/asio/doc/requirements/ConstBufferSequence.qbk
/home/amir/boost_1_69_0/libs/asio/doc/requirements/BufferedHandshakeHandler.qbk
/home/amir/boost_1_69_0/libs/asio/doc/requirements/WriteHandler.qbk
/home/amir/boost_1_69_0/libs/asio/doc/requirements/ShutdownHandler.qbk
/home/amir/boost_1_69_0/libs/asio/doc/requirements/WaitHandler.qbk
/home/amir/boost_1_69_0/libs/asio/doc/requirements/Handler.qbk
/home/amir/boost_1_69_0/libs/asio/doc/using.qbk
/home/amir/boost_1_69_0/libs/asio/doc/examples.qbk
/home/amir/boost_1_69_0/libs/asio/doc/tutorial.qbk
/home/amir/boost_1_69_0/libs/asio/example/cpp17/coroutines_ts/refactored_echo_server.cpp
/home/amir/boost_1_69_0/libs/asio/example/cpp17/coroutines_ts/range_based_for.cpp
/home/amir/boost_1_69_0/libs/asio/example/cpp17/coroutines_ts/chat_server.cpp
/home/amir/boost_1_69_0/libs/asio/example/cpp17/coroutines_ts/double_buffered_echo_server.cpp
/home/amir/boost_1_69_0/libs/asio/example/cpp17/coroutines_ts/echo_server.cpp
/home/amir/boost_1_69_0/libs/asio/example/cpp11/buffers/reference_counted.cpp
/home/amir/boost_1_69_0/libs/asio/example/cpp11/fork/process_per_connection.cpp
/home/amir/boost_1_69_0/libs/asio/example/cpp11/fork/daemon.cpp
/home/amir/boost_1_69_0/libs/asio/example/cpp11/executors/bank_account_1.cpp
/home/amir/boost_1_69_0/libs/asio/example/cpp11/executors/fork_join.cpp
/home/amir/boost_1_69_0/libs/asio/example/cpp11/executors/actor.cpp
/home/amir/boost_1_69_0/libs/asio/example/cpp11/executors/priority_scheduler.cpp
/home/amir/boost_1_69_0/libs/asio/example/cpp11/executors/pipeline.cpp
/home/amir/boost_1_69_0/libs/asio/example/cpp11/executors/bank_account_2.cpp
/home/amir/boost_1_69_0/libs/asio/example/cpp11/spawn/parallel_grep.cpp
/home/amir/boost_1_69_0/libs/asio/example/cpp11/spawn/echo_server.cpp
/home/amir/boost_1_69_0/libs/asio/example/cpp11/futures/daytime_client.cpp
/home/amir/boost_1_69_0/libs/asio/example/cpp11/local/stream_server.cpp
/home/amir/boost_1_69_0/libs/asio/example/cpp11/local/stream_client.cpp
/home/amir/boost_1_69_0/libs/asio/example/cpp11/local/iostream_client.cpp
/home/amir/boost_1_69_0/libs/asio/example/cpp11/local/connect_pair.cpp
/home/amir/boost_1_69_0/libs/asio/example/cpp11/timers/time_t_timer.cpp
/home/amir/boost_1_69_0/libs/asio/example/cpp11/nonblocking/third_party_lib.cpp
/home/amir/boost_1_69_0/libs/asio/example/cpp11/ssl/client.cpp
/home/amir/boost_1_69_0/libs/asio/example/cpp11/ssl/server.cpp
/home/amir/boost_1_69_0/libs/asio/example/cpp11/operations/composed_5.cpp
/home/amir/boost_1_69_0/libs/asio/example/cpp11/operations/composed_3.cpp
/home/amir/boost_1_69_0/libs/asio/example/cpp11/operations/composed_4.cpp
/home/amir/boost_1_69_0/libs/asio/example/cpp11/operations/composed_1.cpp
/home/amir/boost_1_69_0/libs/asio/example/cpp11/operations/composed_2.cpp
/home/amir/boost_1_69_0/libs/asio/example/cpp11/handler_tracking/async_tcp_echo_server.cpp
/home/amir/boost_1_69_0/libs/asio/example/cpp11/handler_tracking/custom_tracking.hpp
/home/amir/boost_1_69_0/libs/asio/example/cpp11/socks4/sync_client.cpp
/home/amir/boost_1_69_0/libs/asio/example/cpp11/socks4/socks4.hpp
/home/amir/boost_1_69_0/libs/asio/example/cpp11/http/server/reply.cpp
/home/amir/boost_1_69_0/libs/asio/example/cpp11/http/server/server.hpp
/home/amir/boost_1_69_0/libs/asio/example/cpp11/http/server/connection.cpp
/home/amir/boost_1_69_0/libs/asio/example/cpp11/http/server/reply.hpp
/home/amir/boost_1_69_0/libs/asio/example/cpp11/http/server/connection.hpp
/home/amir/boost_1_69_0/libs/asio/example/cpp11/http/server/server.cpp
/home/amir/boost_1_69_0/libs/asio/example/cpp11/chat/chat_server.cpp
/home/amir/boost_1_69_0/libs/asio/example/cpp11/chat/chat_client.cpp
/home/amir/boost_1_69_0/libs/asio/example/cpp11/timeouts/server.cpp
/home/amir/boost_1_69_0/libs/asio/example/cpp11/timeouts/blocking_tcp_client.cpp
/home/amir/boost_1_69_0/libs/asio/example/cpp11/timeouts/async_tcp_client.cpp
/home/amir/boost_1_69_0/libs/asio/example/cpp11/timeouts/blocking_token_tcp_client.cpp
/home/amir/boost_1_69_0/libs/asio/example/cpp11/timeouts/blocking_udp_client.cpp
/home/amir/boost_1_69_0/libs/asio/example/cpp11/iostreams/http_client.cpp
/home/amir/boost_1_69_0/libs/asio/example/cpp11/invocation/prioritised_handlers.cpp
/home/amir/boost_1_69_0/libs/asio/example/cpp11/echo/blocking_tcp_echo_server.cpp
/home/amir/boost_1_69_0/libs/asio/example/cpp11/echo/blocking_tcp_echo_client.cpp
/home/amir/boost_1_69_0/libs/asio/example/cpp11/echo/async_tcp_echo_server.cpp
/home/amir/boost_1_69_0/libs/asio/example/cpp11/echo/blocking_udp_echo_client.cpp
/home/amir/boost_1_69_0/libs/asio/example/cpp11/echo/async_udp_echo_server.cpp
/home/amir/boost_1_69_0/libs/asio/example/cpp11/echo/blocking_udp_echo_server.cpp
/home/amir/boost_1_69_0/libs/asio/example/cpp11/multicast/sender.cpp
/home/amir/boost_1_69_0/libs/asio/example/cpp11/multicast/receiver.cpp
/home/amir/boost_1_69_0/libs/asio/example/cpp11/allocation/server.cpp
/home/amir/boost_1_69_0/libs/asio/example/cpp03/buffers/reference_counted.cpp
/home/amir/boost_1_69_0/libs/asio/example/cpp03/fork/process_per_connection.cpp
/home/amir/boost_1_69_0/libs/asio/example/cpp03/fork/daemon.cpp
/home/amir/boost_1_69_0/libs/asio/example/cpp03/spawn/parallel_grep.cpp
/home/amir/boost_1_69_0/libs/asio/example/cpp03/spawn/echo_server.cpp
/home/amir/boost_1_69_0/libs/asio/example/cpp03/local/stream_server.cpp
/home/amir/boost_1_69_0/libs/asio/example/cpp03/local/stream_client.cpp
/home/amir/boost_1_69_0/libs/asio/example/cpp03/local/iostream_client.cpp
/home/amir/boost_1_69_0/libs/asio/example/cpp03/local/connect_pair.cpp
/home/amir/boost_1_69_0/libs/asio/example/cpp03/timers/time_t_timer.cpp
/home/amir/boost_1_69_0/libs/asio/example/cpp03/nonblocking/third_party_lib.cpp
/home/amir/boost_1_69_0/libs/asio/example/cpp03/porthopper/client.cpp
/home/amir/boost_1_69_0/libs/asio/example/cpp03/porthopper/protocol.hpp
/home/amir/boost_1_69_0/libs/asio/example/cpp03/porthopper/server.cpp
/home/amir/boost_1_69_0/libs/asio/example/cpp03/windows/transmit_file.cpp
/home/amir/boost_1_69_0/libs/asio/example/cpp03/services/daytime_client.cpp
/home/amir/boost_1_69_0/libs/asio/example/cpp03/services/basic_logger.hpp
/home/amir/boost_1_69_0/libs/asio/example/cpp03/services/logger_service.hpp
/home/amir/boost_1_69_0/libs/asio/example/cpp03/services/logger_service.cpp
/home/amir/boost_1_69_0/libs/asio/example/cpp03/tutorial/timer2/timer.cpp
/home/amir/boost_1_69_0/libs/asio/example/cpp03/tutorial/timer5/timer.cpp
/home/amir/boost_1_69_0/libs/asio/example/cpp03/tutorial/timer_dox.txt
/home/amir/boost_1_69_0/libs/asio/example/cpp03/tutorial/daytime_dox.txt
/home/amir/boost_1_69_0/libs/asio/example/cpp03/tutorial/daytime1/client.cpp
/home/amir/boost_1_69_0/libs/asio/example/cpp03/tutorial/daytime2/server.cpp
/home/amir/boost_1_69_0/libs/asio/example/cpp03/tutorial/timer3/timer.cpp
/home/amir/boost_1_69_0/libs/asio/example/cpp03/tutorial/timer1/timer.cpp
/home/amir/boost_1_69_0/libs/asio/example/cpp03/tutorial/daytime5/server.cpp
/home/amir/boost_1_69_0/libs/asio/example/cpp03/tutorial/daytime7/server.cpp
/home/amir/boost_1_69_0/libs/asio/example/cpp03/tutorial/timer4/timer.cpp
/home/amir/boost_1_69_0/libs/asio/example/cpp03/tutorial/daytime4/client.cpp
/home/amir/boost_1_69_0/libs/asio/example/cpp03/tutorial/daytime6/server.cpp
/home/amir/boost_1_69_0/libs/asio/example/cpp03/tutorial/daytime3/server.cpp
/home/amir/boost_1_69_0/libs/asio/example/cpp03/ssl/client.cpp
/home/amir/boost_1_69_0/libs/asio/example/cpp03/ssl/server.cpp
/home/amir/boost_1_69_0/libs/asio/example/cpp03/socks4/sync_client.cpp
/home/amir/boost_1_69_0/libs/asio/example/cpp03/socks4/socks4.hpp
/home/amir/boost_1_69_0/libs/asio/example/cpp03/http/server2/io_context_pool.cpp
/home/amir/boost_1_69_0/libs/asio/example/cpp03/http/server2/reply.cpp
/home/amir/boost_1_69_0/libs/asio/example/cpp03/http/server2/server.hpp
/home/amir/boost_1_69_0/libs/asio/example/cpp03/http/server2/connection.cpp
/home/amir/boost_1_69_0/libs/asio/example/cpp03/http/server2/io_context_pool.hpp
/home/amir/boost_1_69_0/libs/asio/example/cpp03/http/server2/reply.hpp
/home/amir/boost_1_69_0/libs/asio/example/cpp03/http/server2/connection.hpp
/home/amir/boost_1_69_0/libs/asio/example/cpp03/http/server2/server.cpp
/home/amir/boost_1_69_0/libs/asio/example/cpp03/http/server3/reply.cpp
/home/amir/boost_1_69_0/libs/asio/example/cpp03/http/server3/server.hpp
/home/amir/boost_1_69_0/libs/asio/example/cpp03/http/server3/connection.cpp
/home/amir/boost_1_69_0/libs/asio/example/cpp03/http/server3/reply.hpp
/home/amir/boost_1_69_0/libs/asio/example/cpp03/http/server3/connection.hpp
/home/amir/boost_1_69_0/libs/asio/example/cpp03/http/server3/server.cpp
/home/amir/boost_1_69_0/libs/asio/example/cpp03/http/client/sync_client.cpp
/home/amir/boost_1_69_0/libs/asio/example/cpp03/http/client/async_client.cpp
/home/amir/boost_1_69_0/libs/asio/example/cpp03/http/server/reply.cpp
/home/amir/boost_1_69_0/libs/asio/example/cpp03/http/server/server.hpp
/home/amir/boost_1_69_0/libs/asio/example/cpp03/http/server/connection.cpp
/home/amir/boost_1_69_0/libs/asio/example/cpp03/http/server/reply.hpp
/home/amir/boost_1_69_0/libs/asio/example/cpp03/http/server/connection.hpp
/home/amir/boost_1_69_0/libs/asio/example/cpp03/http/server/server.cpp
/home/amir/boost_1_69_0/libs/asio/example/cpp03/http/server4/reply.cpp
/home/amir/boost_1_69_0/libs/asio/example/cpp03/http/server4/server.hpp
/home/amir/boost_1_69_0/libs/asio/example/cpp03/http/server4/main.cpp
/home/amir/boost_1_69_0/libs/asio/example/cpp03/http/server4/reply.hpp
/home/amir/boost_1_69_0/libs/asio/example/cpp03/http/server4/server.cpp
/home/amir/boost_1_69_0/libs/asio/example/cpp03/http/server4/request_parser.hpp
/home/amir/boost_1_69_0/libs/asio/example/cpp03/chat/chat_server.cpp
/home/amir/boost_1_69_0/libs/asio/example/cpp03/chat/chat_client.cpp
/home/amir/boost_1_69_0/libs/asio/example/cpp03/chat/posix_chat_client.cpp
/home/amir/boost_1_69_0/libs/asio/example/cpp03/timeouts/server.cpp
/home/amir/boost_1_69_0/libs/asio/example/cpp03/timeouts/blocking_tcp_client.cpp
/home/amir/boost_1_69_0/libs/asio/example/cpp03/timeouts/async_tcp_client.cpp
/home/amir/boost_1_69_0/libs/asio/example/cpp03/timeouts/blocking_token_tcp_client.cpp
/home/amir/boost_1_69_0/libs/asio/example/cpp03/timeouts/blocking_udp_client.cpp
/home/amir/boost_1_69_0/libs/asio/example/cpp03/iostreams/daytime_client.cpp
/home/amir/boost_1_69_0/libs/asio/example/cpp03/iostreams/daytime_server.cpp
/home/amir/boost_1_69_0/libs/asio/example/cpp03/iostreams/http_client.cpp
/home/amir/boost_1_69_0/libs/asio/example/cpp03/serialization/client.cpp
/home/amir/boost_1_69_0/libs/asio/example/cpp03/serialization/connection.hpp
/home/amir/boost_1_69_0/libs/asio/example/cpp03/serialization/server.cpp
/home/amir/boost_1_69_0/libs/asio/example/cpp03/invocation/prioritised_handlers.cpp
/home/amir/boost_1_69_0/libs/asio/example/cpp03/echo/blocking_tcp_echo_server.cpp
/home/amir/boost_1_69_0/libs/asio/example/cpp03/echo/blocking_tcp_echo_client.cpp
/home/amir/boost_1_69_0/libs/asio/example/cpp03/echo/async_tcp_echo_server.cpp
/home/amir/boost_1_69_0/libs/asio/example/cpp03/echo/blocking_udp_echo_client.cpp
/home/amir/boost_1_69_0/libs/asio/example/cpp03/echo/async_udp_echo_server.cpp
/home/amir/boost_1_69_0/libs/asio/example/cpp03/echo/blocking_udp_echo_server.cpp
/home/amir/boost_1_69_0/libs/asio/example/cpp03/icmp/ping.cpp
/home/amir/boost_1_69_0/libs/asio/example/cpp03/icmp/ipv4_header.hpp
/home/amir/boost_1_69_0/libs/asio/example/cpp03/multicast/sender.cpp
/home/amir/boost_1_69_0/libs/asio/example/cpp03/multicast/receiver.cpp
/home/amir/boost_1_69_0/libs/asio/example/cpp03/allocation/server.cpp</details>

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
Всего файлы занимают 38Мб. 

<details><summary>Список файлов и вес каждого файла</summary>total 38M
-rw-rw-r-- 1 amir amir 2.6K Feb 17 12:41 libboost_atomic.a
lrwxrwxrwx 1 amir amir   25 Feb 17 12:45 libboost_atomic.so -> libboost_atomic.so.1.69.0
-rwxrwxr-x 1 amir amir  16K Feb 17 12:45 libboost_atomic.so.1.69.0
-rw-rw-r-- 1 amir amir 235K Feb 17 12:50 libboost_chrono.a
lrwxrwxrwx 1 amir amir   25 Feb 17 12:45 libboost_chrono.so -> libboost_chrono.so.1.69.0
-rwxrwxr-x 1 amir amir  61K Feb 17 12:45 libboost_chrono.so.1.69.0
-rw-rw-r-- 1 amir amir 148K Feb 17 12:41 libboost_container.a
lrwxrwxrwx 1 amir amir   28 Feb 17 12:45 libboost_container.so -> libboost_container.so.1.69.0
-rwxrwxr-x 1 amir amir 100K Feb 17 12:45 libboost_container.so.1.69.0
-rw-rw-r-- 1 amir amir  21K Feb 17 12:41 libboost_context.a
lrwxrwxrwx 1 amir amir   26 Feb 17 12:45 libboost_context.so -> libboost_context.so.1.69.0
-rwxrwxr-x 1 amir amir  24K Feb 17 12:45 libboost_context.so.1.69.0
-rw-rw-r-- 1 amir amir 330K Feb 17 12:41 libboost_contract.a
lrwxrwxrwx 1 amir amir   27 Feb 17 12:45 libboost_contract.so -> libboost_contract.so.1.69.0
-rwxrwxr-x 1 amir amir 176K Feb 17 12:45 libboost_contract.so.1.69.0
-rw-rw-r-- 1 amir amir 152K Feb 17 12:41 libboost_date_time.a
lrwxrwxrwx 1 amir amir   28 Feb 17 12:45 libboost_date_time.so -> libboost_date_time.so.1.69.0
-rwxrwxr-x 1 amir amir  89K Feb 17 12:45 libboost_date_time.so.1.69.0
-rw-rw-r-- 1 amir amir 1.7K Feb 17 12:45 libboost_exception.a
-rw-rw-r-- 1 amir amir 231K Feb 17 12:41 libboost_fiber.a
lrwxrwxrwx 1 amir amir   24 Feb 17 12:46 libboost_fiber.so -> libboost_fiber.so.1.69.0
-rwxrwxr-x 1 amir amir  99K Feb 17 12:46 libboost_fiber.so.1.69.0
-rw-rw-r-- 1 amir amir 414K Feb 17 12:41 libboost_filesystem.a
lrwxrwxrwx 1 amir amir   29 Feb 17 12:46 libboost_filesystem.so -> libboost_filesystem.so.1.69.0
-rwxrwxr-x 1 amir amir 154K Feb 17 12:46 libboost_filesystem.so.1.69.0
-rw-rw-r-- 1 amir amir 845K Feb 17 12:42 libboost_graph.a
lrwxrwxrwx 1 amir amir   24 Feb 17 12:46 libboost_graph.so -> libboost_graph.so.1.69.0
-rwxrwxr-x 1 amir amir 394K Feb 17 12:46 libboost_graph.so.1.69.0
-rw-rw-r-- 1 amir amir 170K Feb 17 12:42 libboost_iostreams.a
lrwxrwxrwx 1 amir amir   28 Feb 17 12:46 libboost_iostreams.so -> libboost_iostreams.so.1.69.0
-rwxrwxr-x 1 amir amir  88K Feb 17 12:46 libboost_iostreams.so.1.69.0
-rw-rw-r-- 1 amir amir 2.0M Feb 17 12:42 libboost_locale.a
lrwxrwxrwx 1 amir amir   25 Feb 17 12:47 libboost_locale.so -> libboost_locale.so.1.69.0
-rwxrwxr-x 1 amir amir 889K Feb 17 12:47 libboost_locale.so.1.69.0
-rw-rw-r-- 1 amir amir 541K Feb 17 12:44 libboost_math_c99.a
-rw-rw-r-- 1 amir amir 448K Feb 17 12:44 libboost_math_c99f.a
lrwxrwxrwx 1 amir amir   28 Feb 17 12:49 libboost_math_c99f.so -> libboost_math_c99f.so.1.69.0
-rwxrwxr-x 1 amir amir 103K Feb 17 12:49 libboost_math_c99f.so.1.69.0
-rw-rw-r-- 1 amir amir 463K Feb 17 12:44 libboost_math_c99l.a
lrwxrwxrwx 1 amir amir   28 Feb 17 12:49 libboost_math_c99l.so -> libboost_math_c99l.so.1.69.0
-rwxrwxr-x 1 amir amir  99K Feb 17 12:49 libboost_math_c99l.so.1.69.0
lrwxrwxrwx 1 amir amir   27 Feb 17 12:49 libboost_math_c99.so -> libboost_math_c99.so.1.69.0
-rwxrwxr-x 1 amir amir 121K Feb 17 12:49 libboost_math_c99.so.1.69.0
-rw-rw-r-- 1 amir amir 2.7M Feb 17 12:44 libboost_math_tr1.a
-rw-rw-r-- 1 amir amir 2.6M Feb 17 12:44 libboost_math_tr1f.a
lrwxrwxrwx 1 amir amir   28 Feb 17 12:48 libboost_math_tr1f.so -> libboost_math_tr1f.so.1.69.0
-rwxrwxr-x 1 amir amir 534K Feb 17 12:48 libboost_math_tr1f.so.1.69.0
-rw-rw-r-- 1 amir amir 2.7M Feb 17 12:44 libboost_math_tr1l.a
lrwxrwxrwx 1 amir amir   28 Feb 17 12:49 libboost_math_tr1l.so -> libboost_math_tr1l.so.1.69.0
-rwxrwxr-x 1 amir amir 527K Feb 17 12:49 libboost_math_tr1l.so.1.69.0
lrwxrwxrwx 1 amir amir   27 Feb 17 12:48 libboost_math_tr1.so -> libboost_math_tr1.so.1.69.0
-rwxrwxr-x 1 amir amir 541K Feb 17 12:48 libboost_math_tr1.so.1.69.0
-rw-rw-r-- 1 amir amir 212K Feb 17 12:45 libboost_prg_exec_monitor.a
lrwxrwxrwx 1 amir amir   35 Feb 17 12:49 libboost_prg_exec_monitor.so -> libboost_prg_exec_monitor.so.1.69.0
-rwxrwxr-x 1 amir amir 115K Feb 17 12:49 libboost_prg_exec_monitor.so.1.69.0
-rw-rw-r-- 1 amir amir 1.6M Feb 17 12:44 libboost_program_options.a
lrwxrwxrwx 1 amir amir   34 Feb 17 12:49 libboost_program_options.so -> libboost_program_options.so.1.69.0
-rwxrwxr-x 1 amir amir 672K Feb 17 12:49 libboost_program_options.so.1.69.0
-rw-rw-r-- 1 amir amir  80K Feb 17 12:44 libboost_random.a
lrwxrwxrwx 1 amir amir   25 Feb 17 12:49 libboost_random.so -> libboost_random.so.1.69.0
-rwxrwxr-x 1 amir amir  56K Feb 17 12:49 libboost_random.so.1.69.0
-rw-rw-r-- 1 amir amir 2.7M Feb 17 12:42 libboost_regex.a
lrwxrwxrwx 1 amir amir   24 Feb 17 12:46 libboost_regex.so -> libboost_regex.so.1.69.0
-rwxrwxr-x 1 amir amir 1.2M Feb 17 12:46 libboost_regex.so.1.69.0
-rw-rw-r-- 1 amir amir 1.2M Feb 17 12:45 libboost_serialization.a
lrwxrwxrwx 1 amir amir   32 Feb 17 12:49 libboost_serialization.so -> libboost_serialization.so.1.69.0
-rwxrwxr-x 1 amir amir 488K Feb 17 12:49 libboost_serialization.so.1.69.0
-rw-rw-r-- 1 amir amir  24K Feb 17 12:45 libboost_stacktrace_addr2line.a
lrwxrwxrwx 1 amir amir   39 Feb 17 12:49 libboost_stacktrace_addr2line.so -> libboost_stacktrace_addr2line.so.1.69.0
-rwxrwxr-x 1 amir amir  32K Feb 17 12:49 libboost_stacktrace_addr2line.so.1.69.0
-rw-rw-r-- 1 amir amir  20K Feb 17 12:45 libboost_stacktrace_backtrace.a
lrwxrwxrwx 1 amir amir   39 Feb 17 12:49 libboost_stacktrace_backtrace.so -> libboost_stacktrace_backtrace.so.1.69.0
-rwxrwxr-x 1 amir amir 108K Feb 17 12:49 libboost_stacktrace_backtrace.so.1.69.0
-rw-rw-r-- 1 amir amir  14K Feb 17 12:45 libboost_stacktrace_basic.a
lrwxrwxrwx 1 amir amir   35 Feb 17 12:49 libboost_stacktrace_basic.so -> libboost_stacktrace_basic.so.1.69.0
-rwxrwxr-x 1 amir amir  22K Feb 17 12:49 libboost_stacktrace_basic.so.1.69.0
-rw-rw-r-- 1 amir amir 2.8K Feb 17 12:45 libboost_stacktrace_noop.a
lrwxrwxrwx 1 amir amir   34 Feb 17 12:49 libboost_stacktrace_noop.so -> libboost_stacktrace_noop.so.1.69.0
-rwxrwxr-x 1 amir amir  16K Feb 17 12:49 libboost_stacktrace_noop.so.1.69.0
-rw-rw-r-- 1 amir amir 1.5K Feb 17 12:49 libboost_system.a
lrwxrwxrwx 1 amir amir   25 Feb 17 12:45 libboost_system.so -> libboost_system.so.1.69.0
-rwxrwxr-x 1 amir amir  15K Feb 17 12:45 libboost_system.so.1.69.0
-rw-rw-r-- 1 amir amir 2.3M Feb 17 12:50 libboost_test_exec_monitor.a
-rw-rw-r-- 1 amir amir  53K Feb 17 12:50 libboost_timer.a
lrwxrwxrwx 1 amir amir   24 Feb 17 12:49 libboost_timer.so -> libboost_timer.so.1.69.0
-rwxrwxr-x 1 amir amir  45K Feb 17 12:49 libboost_timer.so.1.69.0
-rw-rw-r-- 1 amir amir 2.3M Feb 17 12:45 libboost_unit_test_framework.a
lrwxrwxrwx 1 amir amir   38 Feb 17 12:50 libboost_unit_test_framework.so -> libboost_unit_test_framework.so.1.69.0
-rwxrwxr-x 1 amir amir 949K Feb 17 12:50 libboost_unit_test_framework.so.1.69.0
-rw-rw-r-- 1 amir amir 4.5M Feb 17 12:41 libboost_wave.a
-rw-rw-r-- 1 amir amir 793K Feb 17 12:45 libboost_wserialization.a
lrwxrwxrwx 1 amir amir   33 Feb 17 12:49 libboost_wserialization.so -> libboost_wserialization.so.1.69.0
-rwxrwxr-x 1 amir amir 339K Feb 17 12:49 libboost_wserialization.so.1.69.0
drwxrwxr-x 3 amir amir 4.0K Feb 17 13:06 reports
drwxrwxr-x 3 amir amir 4.0K Feb 17 13:04 tasks</details>

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
