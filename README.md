## Laboratory work I
___

**1. Скачайте библиотеку *boost* с помощью утилиты **wget**. Адрес для скачивания `https://sourceforge.net/projects/boost/files/boost/1.69.0/boost_1_69_0.tar.gz`.**

```bash
$ wget https://sourceforge.net/projects/boost/files/boost/1.78.0/boost_1_78_0.tar.gz
```



**2. Разархивируйте скаченный файл в директорию `~/boost_1_78_0`**

```bash
$ tar -xvf boost_1_78_0.tar.gz
$ rm -rf *.gz
```

**3. Подсчитайте количество файлов в директории `~/boost_1_78_0`  _не включая_ вложенные директории.**
```bash
$ find boost_1_78_0 -not -type d | wc -l

>> 71039
```

4. **Подсчитайте количество файлов в директории `~/boost_1_78_0` _включая_ вложенные директории.**
```bash
$ find boost_1_78_0 -not -type d | wc -l 

>> 77723

```

5. **Подсчитайте количество заголовочных файлов, файлов с расширением `.cpp`, сколько остальных файлов (не заголовочных и не `.cpp`). **

```bash
$ find boost_1_78_0 -name '*.h' -o -name '*.hpp'  | wc -l 

>> 16789
```
```bash
$ find boost_1_78_0 -name '*.cpp'  | wc -l 

>> 16267
```
```bash
$ find boost_1_78_0 -not -type d -a -not -name '*.h' -a -not -name '*.hpp' -a -not -name '*.cpp'  | wc -l

>> 37983
```
6. **Найдите полный пусть до файла `any.hpp` внутри библиотеки *boost*.**

```bash 
$ find `pwd`/boost_1_78_0/boost -name 'any.hpp'
```

```
*/home/user/TIMP/lab01/boost_1_78_0/boost/any.hpp
/home/user/TIMP/lab01/boost_1_78_0/boost/fusion/include/any.hpp
/home/user/TIMP/lab01/boost_1_78_0/boost/fusion/algorithm/query/any.hpp
/home/user/TIMP/lab01/boost_1_78_0/boost/fusion/algorithm/query/detail/any.hpp
/home/user/TIMP/lab01/boost_1_78_0/boost/hana/any.hpp
/home/user/TIMP/lab01/boost_1_78_0/boost/hana/fwd/any.hpp
/home/user/TIMP/lab01/boost_1_78_0/boost/type_erasure/any.hpp
/home/user/TIMP/lab01/boost_1_78_0/boost/xpressive/detail/utility/any.hpp
/home/user/TIMP/lab01/boost_1_78_0/boost/spirit/home/support/algorithm/any.hpp
/home/user/TIMP/lab01/boost_1_78_0/boost/proto/detail/any.hpp
/home/user/TIMP/lab01/boost_1_78_0/boost/geometry/geometries/adapted/detail/any.hpp*
```

**7. Выведите в консоль все файлы, где упоминается последовательность.**

```bash 
$ grep -l -r "boost::asio"
```

<details> <summary> Вывод: </summary>
doc/html/boost_asio/std_executors.html
doc/html/boost_asio/index.html
doc/html/boost_asio/tutorial/tutdaytime3/src.html
doc/html/boost_asio/tutorial/tutdaytime4.html
doc/html/boost_asio/tutorial/tutdaytime5/src.html
doc/html/boost_asio/tutorial/tutdaytime7.html
doc/html/boost_asio/tutorial/tuttimer2.html
doc/html/boost_asio/tutorial/tuttimer1.html
doc/html/boost_asio/tutorial/tuttimer5/src.html
doc/html/boost_asio/tutorial/tutdaytime6.html
doc/html/boost_asio/tutorial/tutdaytime1/src.html
doc/html/boost_asio/tutorial/tutdaytime5.html
doc/html/boost_asio/tutorial/tuttimer1/src.html
doc/html/boost_asio/tutorial/tuttimer5.html
doc/html/boost_asio/tutorial/tutdaytime6/src.html
doc/html/boost_asio/tutorial/tutdaytime1.html
doc/html/boost_asio/tutorial/tutdaytime2.html
doc/html/boost_asio/tutorial/tutdaytime2/src.html
doc/html/boost_asio/tutorial/tutdaytime4/src.html
doc/html/boost_asio/tutorial/tuttimer4.html
doc/html/boost_asio/tutorial/tuttimer2/src.html
doc/html/boost_asio/tutorial/tutdaytime3.html
doc/html/boost_asio/tutorial/tuttimer4/src.html
doc/html/boost_asio/tutorial/tuttimer3/src.html
doc/html/boost_asio/tutorial/tutdaytime7/src.html
doc/html/boost_asio/tutorial/tuttimer3.html
doc/html/boost_asio/reference/basic_socket_acceptor__rebind_executor/other.html
doc/html/boost_asio/reference/transfer_all.html
doc/html/boost_asio/reference/placeholders__endpoint.html
doc/html/boost_asio/reference/query_result.html
doc/html/boost_asio/reference/system_context/add_service.html
doc/html/boost_asio/reference/system_context/make_service.html
doc/html/boost_asio/reference/async_read_until.html
doc/html/boost_asio/reference/MoveAcceptHandler.html
doc/html/boost_asio/reference/ip__basic_resolver/cancel.html
doc/html/boost_asio/reference/basic_deadline_timer/cancel_one/overload2.html
doc/html/boost_asio/reference/basic_deadline_timer/cancel_one/overload1.html
doc/html/boost_asio/reference/basic_deadline_timer/cancel/overload2.html
doc/html/boost_asio/reference/basic_deadline_timer/cancel/overload1.html
doc/html/boost_asio/reference/basic_deadline_timer/expires_from_now/overload2.html
doc/html/boost_asio/reference/basic_deadline_timer/expires_from_now/overload3.html
doc/html/boost_asio/reference/basic_deadline_timer/async_wait.html
doc/html/boost_asio/reference/basic_deadline_timer/expires_at/overload2.html
doc/html/boost_asio/reference/basic_deadline_timer/expires_at/overload3.html
doc/html/boost_asio/reference/experimental__error__channel_category.html
doc/html/boost_asio/reference/WriteHandler.html
doc/html/boost_asio/reference/thread_pool.html
doc/html/boost_asio/reference/experimental__use_coro.html
doc/html/boost_asio/reference/basic_stream_socket/send_buffer_size.html
doc/html/boost_asio/reference/basic_stream_socket/get_option/overload2.html
doc/html/boost_asio/reference/basic_stream_socket/get_option/overload1.html
doc/html/boost_asio/reference/basic_stream_socket/close/overload2.html
doc/html/boost_asio/reference/basic_stream_socket/close/overload1.html
doc/html/boost_asio/reference/basic_stream_socket/linger.html
doc/html/boost_asio/reference/basic_stream_socket/debug.html
doc/html/boost_asio/reference/basic_stream_socket/async_read_some.html
doc/html/boost_asio/reference/basic_stream_socket/read_some/overload1.html
doc/html/boost_asio/reference/basic_stream_socket/receive_low_watermark.html
doc/html/boost_asio/reference/basic_stream_socket/do_not_route.html
doc/html/boost_asio/reference/basic_stream_socket/native_non_blocking/overload2.html
doc/html/boost_asio/reference/basic_stream_socket/native_non_blocking/overload3.html
doc/html/boost_asio/reference/basic_stream_socket/native_non_blocking/overload1.html
doc/html/boost_asio/reference/basic_stream_socket/async_send/overload2.html
doc/html/boost_asio/reference/basic_stream_socket/async_send/overload1.html
doc/html/boost_asio/reference/basic_stream_socket/release/overload2.html
doc/html/boost_asio/reference/basic_stream_socket/release/overload1.html
doc/html/boost_asio/reference/basic_stream_socket/async_connect.html
doc/html/boost_asio/reference/basic_stream_socket/async_receive/overload2.html
doc/html/boost_asio/reference/basic_stream_socket/async_receive/overload1.html
doc/html/boost_asio/reference/basic_stream_socket/bytes_readable.html
doc/html/boost_asio/reference/basic_stream_socket/cancel/overload2.html
doc/html/boost_asio/reference/basic_stream_socket/cancel/overload1.html
doc/html/boost_asio/reference/basic_stream_socket/enable_connection_aborted.html
doc/html/boost_asio/reference/basic_stream_socket/local_endpoint/overload2.html
doc/html/boost_asio/reference/basic_stream_socket/local_endpoint/overload1.html
doc/html/boost_asio/reference/basic_stream_socket/receive/overload2.html
doc/html/boost_asio/reference/basic_stream_socket/receive/overload1.html
doc/html/boost_asio/reference/basic_stream_socket/send_low_watermark.html
doc/html/boost_asio/reference/basic_stream_socket/async_write_some.html
doc/html/boost_asio/reference/basic_stream_socket/keep_alive.html
doc/html/boost_asio/reference/basic_stream_socket/write_some/overload1.html
doc/html/boost_asio/reference/basic_stream_socket/wait/overload2.html
doc/html/boost_asio/reference/basic_stream_socket/wait/overload1.html
doc/html/boost_asio/reference/basic_stream_socket/open/overload2.html
doc/html/boost_asio/reference/basic_stream_socket/open/overload1.html
doc/html/boost_asio/reference/basic_stream_socket/async_wait.html
doc/html/boost_asio/reference/basic_stream_socket/set_option/overload2.html
doc/html/boost_asio/reference/basic_stream_socket/set_option/overload1.html
doc/html/boost_asio/reference/basic_stream_socket/non_blocking/overload2.html
doc/html/boost_asio/reference/basic_stream_socket/non_blocking/overload3.html
doc/html/boost_asio/reference/basic_stream_socket/non_blocking/overload1.html
doc/html/boost_asio/reference/basic_stream_socket/broadcast.html
doc/html/boost_asio/reference/basic_stream_socket/shutdown/overload2.html
doc/html/boost_asio/reference/basic_stream_socket/shutdown/overload1.html
doc/html/boost_asio/reference/basic_stream_socket/remote_endpoint/overload2.html
doc/html/boost_asio/reference/basic_stream_socket/remote_endpoint/overload1.html
doc/html/boost_asio/reference/basic_stream_socket/out_of_band_inline.html
doc/html/boost_asio/reference/basic_stream_socket/connect/overload2.html
doc/html/boost_asio/reference/basic_stream_socket/connect/overload1.html
doc/html/boost_asio/reference/basic_stream_socket/io_control/overload2.html
doc/html/boost_asio/reference/basic_stream_socket/io_control/overload1.html
doc/html/boost_asio/reference/basic_stream_socket/bind/overload2.html
doc/html/boost_asio/reference/basic_stream_socket/bind/overload1.html
doc/html/boost_asio/reference/basic_stream_socket/receive_buffer_size.html
doc/html/boost_asio/reference/basic_stream_socket/send/overload2.html
doc/html/boost_asio/reference/basic_stream_socket/send/overload1.html
doc/html/boost_asio/reference/basic_stream_socket/reuse_address.html
doc/html/boost_asio/reference/is_error_code_enum_lt__netdb_errors__gt_/value.html
doc/html/boost_asio/reference/RangeConnectHandler.html
doc/html/boost_asio/reference/basic_socket_acceptor/send_buffer_size.html
doc/html/boost_asio/reference/basic_socket_acceptor/get_option/overload2.html
doc/html/boost_asio/reference/basic_socket_acceptor/get_option/overload1.html
doc/html/boost_asio/reference/basic_socket_acceptor/close/overload2.html
doc/html/boost_asio/reference/basic_socket_acceptor/linger.html
doc/html/boost_asio/reference/basic_socket_acceptor/listen/overload2.html
doc/html/boost_asio/reference/basic_socket_acceptor/debug.html
doc/html/boost_asio/reference/basic_socket_acceptor/receive_low_watermark.html
doc/html/boost_asio/reference/basic_socket_acceptor/do_not_route.html
doc/html/boost_asio/reference/basic_socket_acceptor/async_accept/overload7.html
doc/html/boost_asio/reference/basic_socket_acceptor/async_accept/overload6.html
doc/html/boost_asio/reference/basic_socket_acceptor/async_accept/overload4.html
doc/html/boost_asio/reference/basic_socket_acceptor/async_accept/overload3.html
doc/html/boost_asio/reference/basic_socket_acceptor/async_accept/overload8.html
doc/html/boost_asio/reference/basic_socket_acceptor/async_accept/overload5.html
doc/html/boost_asio/reference/basic_socket_acceptor/async_accept/overload1.html
doc/html/boost_asio/reference/basic_socket_acceptor/native_non_blocking/overload2.html
doc/html/boost_asio/reference/basic_socket_acceptor/native_non_blocking/overload3.html
doc/html/boost_asio/reference/basic_socket_acceptor/native_non_blocking/overload1.html
doc/html/boost_asio/reference/basic_socket_acceptor/release/overload2.html
doc/html/boost_asio/reference/basic_socket_acceptor/release/overload1.html
doc/html/boost_asio/reference/basic_socket_acceptor/bytes_readable.html
doc/html/boost_asio/reference/basic_socket_acceptor/cancel/overload2.html
doc/html/boost_asio/reference/basic_socket_acceptor/cancel/overload1.html
doc/html/boost_asio/reference/basic_socket_acceptor/enable_connection_aborted.html
doc/html/boost_asio/reference/basic_socket_acceptor/local_endpoint/overload2.html
doc/html/boost_asio/reference/basic_socket_acceptor/local_endpoint/overload1.html
doc/html/boost_asio/reference/basic_socket_acceptor/send_low_watermark.html
doc/html/boost_asio/reference/basic_socket_acceptor/keep_alive.html
doc/html/boost_asio/reference/basic_socket_acceptor/wait/overload2.html
doc/html/boost_asio/reference/basic_socket_acceptor/wait/overload1.html
doc/html/boost_asio/reference/basic_socket_acceptor/accept/overload2.html
doc/html/boost_asio/reference/basic_socket_acceptor/accept/overload7.html
doc/html/boost_asio/reference/basic_socket_acceptor/accept/overload6.html
doc/html/boost_asio/reference/basic_socket_acceptor/accept/overload4.html
doc/html/boost_asio/reference/basic_socket_acceptor/accept/overload13.html
doc/html/boost_asio/reference/basic_socket_acceptor/accept/overload9.html
doc/html/boost_asio/reference/basic_socket_acceptor/accept/overload10.html
doc/html/boost_asio/reference/basic_socket_acceptor/accept/overload3.html
doc/html/boost_asio/reference/basic_socket_acceptor/accept/overload12.html
doc/html/boost_asio/reference/basic_socket_acceptor/accept/overload16.html
doc/html/boost_asio/reference/basic_socket_acceptor/accept/overload15.html
doc/html/boost_asio/reference/basic_socket_acceptor/accept/overload8.html
doc/html/boost_asio/reference/basic_socket_acceptor/accept/overload14.html
doc/html/boost_asio/reference/basic_socket_acceptor/accept/overload11.html
doc/html/boost_asio/reference/basic_socket_acceptor/accept/overload5.html
doc/html/boost_asio/reference/basic_socket_acceptor/accept/overload1.html
doc/html/boost_asio/reference/basic_socket_acceptor/open/overload2.html
doc/html/boost_asio/reference/basic_socket_acceptor/open/overload1.html
doc/html/boost_asio/reference/basic_socket_acceptor/async_wait.html
doc/html/boost_asio/reference/basic_socket_acceptor/set_option/overload2.html
doc/html/boost_asio/reference/basic_socket_acceptor/set_option/overload1.html
doc/html/boost_asio/reference/basic_socket_acceptor/non_blocking/overload2.html
doc/html/boost_asio/reference/basic_socket_acceptor/non_blocking/overload3.html
doc/html/boost_asio/reference/basic_socket_acceptor/non_blocking/overload1.html
doc/html/boost_asio/reference/basic_socket_acceptor/broadcast.html
doc/html/boost_asio/reference/basic_socket_acceptor/out_of_band_inline.html
doc/html/boost_asio/reference/basic_socket_acceptor/io_control/overload2.html
doc/html/boost_asio/reference/basic_socket_acceptor/io_control/overload1.html
doc/html/boost_asio/reference/basic_socket_acceptor/bind/overload2.html
doc/html/boost_asio/reference/basic_socket_acceptor/bind/overload1.html
doc/html/boost_asio/reference/basic_socket_acceptor/receive_buffer_size.html
doc/html/boost_asio/reference/basic_socket_acceptor/reuse_address.html
doc/html/boost_asio/reference/mutable_buffer.html
doc/html/boost_asio/reference/deadline_timer.html
doc/html/boost_asio/reference/basic_socket/send_buffer_size.html
doc/html/boost_asio/reference/basic_socket/get_option/overload2.html
doc/html/boost_asio/reference/basic_socket/get_option/overload1.html
doc/html/boost_asio/reference/basic_socket/close/overload2.html
doc/html/boost_asio/reference/basic_socket/close/overload1.html
doc/html/boost_asio/reference/basic_socket/linger.html
doc/html/boost_asio/reference/basic_socket/debug.html
doc/html/boost_asio/reference/basic_socket/receive_low_watermark.html
doc/html/boost_asio/reference/basic_socket/do_not_route.html
doc/html/boost_asio/reference/basic_socket/native_non_blocking/overload2.html
doc/html/boost_asio/reference/basic_socket/native_non_blocking/overload3.html
doc/html/boost_asio/reference/basic_socket/native_non_blocking/overload1.html
doc/html/boost_asio/reference/basic_socket/release/overload2.html
doc/html/boost_asio/reference/basic_socket/release/overload1.html
doc/html/boost_asio/reference/basic_socket/async_connect.html
doc/html/boost_asio/reference/basic_socket/bytes_readable.html
doc/html/boost_asio/reference/basic_socket/cancel/overload2.html
doc/html/boost_asio/reference/basic_socket/cancel/overload1.html
doc/html/boost_asio/reference/basic_socket/enable_connection_aborted.html
doc/html/boost_asio/reference/basic_socket/local_endpoint/overload2.html
doc/html/boost_asio/reference/basic_socket/local_endpoint/overload1.html
doc/html/boost_asio/reference/basic_socket/send_low_watermark.html
doc/html/boost_asio/reference/basic_socket/keep_alive.html
doc/html/boost_asio/reference/basic_socket/wait/overload2.html
doc/html/boost_asio/reference/basic_socket/wait/overload1.html
doc/html/boost_asio/reference/basic_socket/open/overload2.html
doc/html/boost_asio/reference/basic_socket/open/overload1.html
doc/html/boost_asio/reference/basic_socket/async_wait.html
doc/html/boost_asio/reference/basic_socket/set_option/overload2.html
doc/html/boost_asio/reference/basic_socket/set_option/overload1.html
doc/html/boost_asio/reference/basic_socket/non_blocking/overload2.html
doc/html/boost_asio/reference/basic_socket/non_blocking/overload3.html
doc/html/boost_asio/reference/basic_socket/non_blocking/overload1.html
doc/html/boost_asio/reference/basic_socket/broadcast.html
doc/html/boost_asio/reference/basic_socket/shutdown/overload2.html
doc/html/boost_asio/reference/basic_socket/shutdown/overload1.html
doc/html/boost_asio/reference/basic_socket/remote_endpoint/overload2.html
doc/html/boost_asio/reference/basic_socket/remote_endpoint/overload1.html
doc/html/boost_asio/reference/basic_socket/out_of_band_inline.html
doc/html/boost_asio/reference/basic_socket/connect/overload2.html
doc/html/boost_asio/reference/basic_socket/connect/overload1.html
doc/html/boost_asio/reference/basic_socket/io_control/overload2.html
doc/html/boost_asio/reference/basic_socket/io_control/overload1.html
doc/html/boost_asio/reference/basic_socket/bind/overload2.html
doc/html/boost_asio/reference/basic_socket/bind/overload1.html
doc/html/boost_asio/reference/basic_socket/receive_buffer_size.html
doc/html/boost_asio/reference/basic_socket/reuse_address.html
doc/html/boost_asio/reference/error__netdb_category.html
doc/html/boost_asio/reference/placeholders__bytes_transferred.html
doc/html/boost_asio/reference/async_read/overload2.html
doc/html/boost_asio/reference/async_read/overload7.html
doc/html/boost_asio/reference/async_read/overload3.html
doc/html/boost_asio/reference/async_read/overload5.html
doc/html/boost_asio/reference/async_read/overload1.html
doc/html/boost_asio/reference/co_spawn/overload2.html
doc/html/boost_asio/reference/co_spawn/overload6.html
doc/html/boost_asio/reference/co_spawn/overload4.html
doc/html/boost_asio/reference/co_spawn/overload3.html
doc/html/boost_asio/reference/co_spawn/overload5.html
doc/html/boost_asio/reference/co_spawn/overload1.html
doc/html/boost_asio/reference/ip__basic_endpoint/basic_endpoint/overload2.html
doc/html/boost_asio/reference/ip__basic_endpoint/basic_endpoint/overload3.html
doc/html/boost_asio/reference/ip__basic_endpoint/address/overload2.html
doc/html/boost_asio/reference/ip__basic_endpoint/address/overload1.html
doc/html/boost_asio/reference/ip__basic_endpoint/address.html
doc/html/boost_asio/reference/ip__basic_endpoint/basic_endpoint.html
doc/html/boost_asio/reference/basic_seq_packet_socket/send_buffer_size.html
doc/html/boost_asio/reference/basic_seq_packet_socket/get_option/overload2.html
doc/html/boost_asio/reference/basic_seq_packet_socket/get_option/overload1.html
doc/html/boost_asio/reference/basic_seq_packet_socket/close/overload2.html
doc/html/boost_asio/reference/basic_seq_packet_socket/close/overload1.html
doc/html/boost_asio/reference/basic_seq_packet_socket/async_send.html
doc/html/boost_asio/reference/basic_seq_packet_socket/linger.html
doc/html/boost_asio/reference/basic_seq_packet_socket/debug.html
doc/html/boost_asio/reference/basic_seq_packet_socket/receive_low_watermark.html
doc/html/boost_asio/reference/basic_seq_packet_socket/do_not_route.html
doc/html/boost_asio/reference/basic_seq_packet_socket/native_non_blocking/overload2.html
doc/html/boost_asio/reference/basic_seq_packet_socket/native_non_blocking/overload3.html
doc/html/boost_asio/reference/basic_seq_packet_socket/native_non_blocking/overload1.html
doc/html/boost_asio/reference/basic_seq_packet_socket/release/overload2.html
doc/html/boost_asio/reference/basic_seq_packet_socket/release/overload1.html
doc/html/boost_asio/reference/basic_seq_packet_socket/async_connect.html
doc/html/boost_asio/reference/basic_seq_packet_socket/async_receive/overload2.html
doc/html/boost_asio/reference/basic_seq_packet_socket/async_receive/overload1.html
doc/html/boost_asio/reference/basic_seq_packet_socket/bytes_readable.html
doc/html/boost_asio/reference/basic_seq_packet_socket/cancel/overload2.html
doc/html/boost_asio/reference/basic_seq_packet_socket/cancel/overload1.html
doc/html/boost_asio/reference/basic_seq_packet_socket/enable_connection_aborted.html
doc/html/boost_asio/reference/basic_seq_packet_socket/local_endpoint/overload2.html
doc/html/boost_asio/reference/basic_seq_packet_socket/local_endpoint/overload1.html
doc/html/boost_asio/reference/basic_seq_packet_socket/receive/overload2.html
doc/html/boost_asio/reference/basic_seq_packet_socket/receive/overload1.html
doc/html/boost_asio/reference/basic_seq_packet_socket/send_low_watermark.html
doc/html/boost_asio/reference/basic_seq_packet_socket/keep_alive.html
doc/html/boost_asio/reference/basic_seq_packet_socket/wait/overload2.html
doc/html/boost_asio/reference/basic_seq_packet_socket/wait/overload1.html
doc/html/boost_asio/reference/basic_seq_packet_socket/open/overload2.html
doc/html/boost_asio/reference/basic_seq_packet_socket/open/overload1.html
doc/html/boost_asio/reference/basic_seq_packet_socket/async_wait.html
doc/html/boost_asio/reference/basic_seq_packet_socket/set_option/overload2.html
doc/html/boost_asio/reference/basic_seq_packet_socket/set_option/overload1.html
doc/html/boost_asio/reference/basic_seq_packet_socket/non_blocking/overload2.html
doc/html/boost_asio/reference/basic_seq_packet_socket/non_blocking/overload3.html
doc/html/boost_asio/reference/basic_seq_packet_socket/non_blocking/overload1.html
doc/html/boost_asio/reference/basic_seq_packet_socket/broadcast.html
doc/html/boost_asio/reference/basic_seq_packet_socket/shutdown/overload2.html
doc/html/boost_asio/reference/basic_seq_packet_socket/shutdown/overload1.html
doc/html/boost_asio/reference/basic_seq_packet_socket/remote_endpoint/overload2.html
doc/html/boost_asio/reference/basic_seq_packet_socket/remote_endpoint/overload1.html
doc/html/boost_asio/reference/basic_seq_packet_socket/out_of_band_inline.html
doc/html/boost_asio/reference/basic_seq_packet_socket/connect/overload2.html
doc/html/boost_asio/reference/basic_seq_packet_socket/connect/overload1.html
doc/html/boost_asio/reference/basic_seq_packet_socket/io_control/overload2.html
doc/html/boost_asio/reference/basic_seq_packet_socket/io_control/overload1.html
doc/html/boost_asio/reference/basic_seq_packet_socket/bind/overload2.html
doc/html/boost_asio/reference/basic_seq_packet_socket/bind/overload1.html
doc/html/boost_asio/reference/basic_seq_packet_socket/receive_buffer_size.html
doc/html/boost_asio/reference/basic_seq_packet_socket/send/overload1.html
doc/html/boost_asio/reference/basic_seq_packet_socket/reuse_address.html
doc/html/boost_asio/reference/this_coro__throw_if_cancelled/overload2.html
doc/html/boost_asio/reference/this_coro__throw_if_cancelled/overload1.html
doc/html/boost_asio/reference/yield_context.html
doc/html/boost_asio/reference/experimental__deferred_t__executor_with_default/default_completion_token_type.html
doc/html/boost_asio/reference/socket_base/send_buffer_size.html
doc/html/boost_asio/reference/socket_base/linger.html
doc/html/boost_asio/reference/socket_base/debug.html
doc/html/boost_asio/reference/socket_base/receive_low_watermark.html
doc/html/boost_asio/reference/socket_base/do_not_route.html
doc/html/boost_asio/reference/socket_base/bytes_readable.html
doc/html/boost_asio/reference/socket_base/enable_connection_aborted.html
doc/html/boost_asio/reference/socket_base/send_low_watermark.html
doc/html/boost_asio/reference/socket_base/keep_alive.html
doc/html/boost_asio/reference/socket_base/broadcast.html
doc/html/boost_asio/reference/socket_base/out_of_band_inline.html
doc/html/boost_asio/reference/socket_base/receive_buffer_size.html
doc/html/boost_asio/reference/socket_base/reuse_address.html
doc/html/boost_asio/reference/windows__basic_stream_handle/close/overload2.html
doc/html/boost_asio/reference/windows__basic_stream_handle/close/overload1.html
doc/html/boost_asio/reference/windows__basic_stream_handle/async_read_some.html
doc/html/boost_asio/reference/windows__basic_stream_handle/read_some/overload1.html
doc/html/boost_asio/reference/windows__basic_stream_handle/cancel/overload2.html
doc/html/boost_asio/reference/windows__basic_stream_handle/cancel/overload1.html
doc/html/boost_asio/reference/windows__basic_stream_handle/async_write_some.html
doc/html/boost_asio/reference/windows__basic_stream_handle/write_some/overload1.html
doc/html/boost_asio/reference/is_error_code_enum_lt__boost__asio__ssl__error__stream_errors__gt_.html
doc/html/boost_asio/reference/basic_signal_set__rebind_executor/other.html
doc/html/boost_asio/reference/basic_waitable_timer.html
doc/html/boost_asio/reference/use_future_t.html
doc/html/boost_asio/reference/Scheduler.html
doc/html/boost_asio/reference/experimental__parallel_group/async_wait.html
doc/html/boost_asio/reference/placeholders__iterator.html
doc/html/boost_asio/reference/read_until.html
doc/html/boost_asio/reference/ip__multicast__leave_group.html
doc/html/boost_asio/reference/async_read_at/overload2.html
doc/html/boost_asio/reference/async_read_at/overload3.html
doc/html/boost_asio/reference/async_read_at/overload1.html
doc/html/boost_asio/reference/io_service.html
doc/html/boost_asio/reference/can_prefer.html
doc/html/boost_asio/reference/io_context.html
doc/html/boost_asio/reference/io_context__strand/strand.html
doc/html/boost_asio/reference/io_context__strand/context.html
doc/html/boost_asio/reference/buffer_sequence_end.html
doc/html/boost_asio/reference/basic_deadline_timer__rebind_executor/other.html
doc/html/boost_asio/reference/async_write_at/overload2.html
doc/html/boost_asio/reference/async_write_at/overload1.html
doc/html/boost_asio/reference/prefer.html
doc/html/boost_asio/reference/is_error_code_enum_lt__basic_errors__gt_.html
doc/html/boost_asio/reference/basic_socket_streambuf/expires_from_now/overload2.html
doc/html/boost_asio/reference/basic_socket_streambuf/expires_at/overload2.html
doc/html/boost_asio/reference/basic_socket_streambuf/expires_after.html
doc/html/boost_asio/reference/async_read_until/overload2.html
doc/html/boost_asio/reference/async_read_until/overload7.html
doc/html/boost_asio/reference/async_read_until/overload6.html
doc/html/boost_asio/reference/async_read_until/overload4.html
doc/html/boost_asio/reference/async_read_until/overload9.html
doc/html/boost_asio/reference/async_read_until/overload10.html
doc/html/boost_asio/reference/async_read_until/overload3.html
doc/html/boost_asio/reference/async_read_until/overload12.html
doc/html/boost_asio/reference/async_read_until/overload8.html
doc/html/boost_asio/reference/async_read_until/overload11.html
doc/html/boost_asio/reference/async_read_until/overload5.html
doc/html/boost_asio/reference/async_read_until/overload1.html
doc/html/boost_asio/reference/experimental__basic_concurrent_channel/cancel.html
doc/html/boost_asio/reference/ssl__host_name_verification.html
doc/html/boost_asio/reference/ReadHandler.html
doc/html/boost_asio/reference/require_result.html
doc/html/boost_asio/reference/basic_serial_port/close/overload2.html
doc/html/boost_asio/reference/basic_serial_port/close/overload1.html
doc/html/boost_asio/reference/basic_serial_port/async_read_some.html
doc/html/boost_asio/reference/basic_serial_port/read_some/overload1.html
doc/html/boost_asio/reference/basic_serial_port/cancel/overload2.html
doc/html/boost_asio/reference/basic_serial_port/cancel/overload1.html
doc/html/boost_asio/reference/basic_serial_port/async_write_some.html
doc/html/boost_asio/reference/basic_serial_port/write_some/overload1.html
doc/html/boost_asio/reference/dynamic_buffer.html
doc/html/boost_asio/reference/is_error_code_enum_lt__misc_errors__gt_/value.html
doc/html/boost_asio/reference/error__misc_category.html
doc/html/boost_asio/reference/generic__raw_protocol.html
doc/html/boost_asio/reference/const_buffers_1/value_type.html
doc/html/boost_asio/reference/experimental__basic_channel/cancel.html
doc/html/boost_asio/reference/signal_set.html
doc/html/boost_asio/reference/generic__datagram_protocol.html
doc/html/boost_asio/reference/execution_context/add_service.html
doc/html/boost_asio/reference/execution_context/make_service.html
doc/html/boost_asio/reference/posix__descriptor_base/bytes_readable.html
doc/html/boost_asio/reference/is_nothrow_require_concept.html
doc/html/boost_asio/reference/ConstBufferSequence.html
doc/html/boost_asio/reference/transfer_at_least.html
doc/html/boost_asio/reference/IteratorConnectHandler.html
doc/html/boost_asio/reference/ip__multicast__enable_loopback.html
doc/html/boost_asio/reference/is_error_code_enum_lt__boost__asio__ssl__error__stream_errors__gt_/value.html
doc/html/boost_asio/reference/error__addrinfo_category.html
doc/html/boost_asio/reference/io_context__work/get_io_context.html
doc/html/boost_asio/reference/io_context__work/work/overload1.html
doc/html/boost_asio/reference/io_context__work/work.html
doc/html/boost_asio/reference/io_context__strand.html
doc/html/boost_asio/reference/is_error_code_enum_lt__misc_errors__gt_.html
doc/html/boost_asio/reference/basic_datagram_socket/send_buffer_size.html
doc/html/boost_asio/reference/basic_datagram_socket/get_option/overload2.html
doc/html/boost_asio/reference/basic_datagram_socket/get_option/overload1.html
doc/html/boost_asio/reference/basic_datagram_socket/close/overload2.html
doc/html/boost_asio/reference/basic_datagram_socket/close/overload1.html
doc/html/boost_asio/reference/basic_datagram_socket/async_send_to/overload1.html
doc/html/boost_asio/reference/basic_datagram_socket/linger.html
doc/html/boost_asio/reference/basic_datagram_socket/debug.html
doc/html/boost_asio/reference/basic_datagram_socket/receive_low_watermark.html
doc/html/boost_asio/reference/basic_datagram_socket/do_not_route.html
doc/html/boost_asio/reference/basic_datagram_socket/native_non_blocking/overload2.html
doc/html/boost_asio/reference/basic_datagram_socket/native_non_blocking/overload3.html
doc/html/boost_asio/reference/basic_datagram_socket/native_non_blocking/overload1.html
doc/html/boost_asio/reference/basic_datagram_socket/async_send/overload1.html
doc/html/boost_asio/reference/basic_datagram_socket/release/overload2.html
doc/html/boost_asio/reference/basic_datagram_socket/release/overload1.html
doc/html/boost_asio/reference/basic_datagram_socket/async_connect.html
doc/html/boost_asio/reference/basic_datagram_socket/async_receive/overload1.html
doc/html/boost_asio/reference/basic_datagram_socket/bytes_readable.html
doc/html/boost_asio/reference/basic_datagram_socket/cancel/overload2.html
doc/html/boost_asio/reference/basic_datagram_socket/cancel/overload1.html
doc/html/boost_asio/reference/basic_datagram_socket/enable_connection_aborted.html
doc/html/boost_asio/reference/basic_datagram_socket/send_to/overload1.html
doc/html/boost_asio/reference/basic_datagram_socket/local_endpoint/overload2.html
doc/html/boost_asio/reference/basic_datagram_socket/local_endpoint/overload1.html
doc/html/boost_asio/reference/basic_datagram_socket/receive/overload1.html
doc/html/boost_asio/reference/basic_datagram_socket/send_low_watermark.html
doc/html/boost_asio/reference/basic_datagram_socket/keep_alive.html
doc/html/boost_asio/reference/basic_datagram_socket/wait/overload2.html
doc/html/boost_asio/reference/basic_datagram_socket/wait/overload1.html
doc/html/boost_asio/reference/basic_datagram_socket/receive_from/overload1.html
doc/html/boost_asio/reference/basic_datagram_socket/open/overload2.html
doc/html/boost_asio/reference/basic_datagram_socket/open/overload1.html
doc/html/boost_asio/reference/basic_datagram_socket/async_wait.html
doc/html/boost_asio/reference/basic_datagram_socket/set_option/overload2.html
doc/html/boost_asio/reference/basic_datagram_socket/set_option/overload1.html
doc/html/boost_asio/reference/basic_datagram_socket/non_blocking/overload2.html
doc/html/boost_asio/reference/basic_datagram_socket/non_blocking/overload3.html
doc/html/boost_asio/reference/basic_datagram_socket/non_blocking/overload1.html
doc/html/boost_asio/reference/basic_datagram_socket/broadcast.html
doc/html/boost_asio/reference/basic_datagram_socket/shutdown/overload2.html
doc/html/boost_asio/reference/basic_datagram_socket/shutdown/overload1.html
doc/html/boost_asio/reference/basic_datagram_socket/remote_endpoint/overload2.html
doc/html/boost_asio/reference/basic_datagram_socket/remote_endpoint/overload1.html
doc/html/boost_asio/reference/basic_datagram_socket/out_of_band_inline.html
doc/html/boost_asio/reference/basic_datagram_socket/connect/overload2.html
doc/html/boost_asio/reference/basic_datagram_socket/connect/overload1.html
doc/html/boost_asio/reference/basic_datagram_socket/io_control/overload2.html
doc/html/boost_asio/reference/basic_datagram_socket/io_control/overload1.html
doc/html/boost_asio/reference/basic_datagram_socket/bind/overload2.html
doc/html/boost_asio/reference/basic_datagram_socket/bind/overload1.html
doc/html/boost_asio/reference/basic_datagram_socket/receive_buffer_size.html
doc/html/boost_asio/reference/basic_datagram_socket/send/overload1.html
doc/html/boost_asio/reference/basic_datagram_socket/reuse_address.html
doc/html/boost_asio/reference/basic_datagram_socket/async_receive_from/overload1.html
doc/html/boost_asio/reference/spawn/overload6.html
doc/html/boost_asio/reference/can_require.html
doc/html/boost_asio/reference/is_error_code_enum_lt__addrinfo_errors__gt_/value.html
doc/html/boost_asio/reference/ssl__stream.html
doc/html/boost_asio/reference/basic_system_executor/query/overload2.html
doc/html/boost_asio/reference/basic_system_executor/query/overload3.html
doc/html/boost_asio/reference/basic_system_executor/query/overload1.html
doc/html/boost_asio/reference/basic_system_executor/execute.html
doc/html/boost_asio/reference/basic_system_executor/query__static/overload2.html
doc/html/boost_asio/reference/basic_system_executor/query__static/overload4.html
doc/html/boost_asio/reference/basic_system_executor/query__static/overload3.html
doc/html/boost_asio/reference/basic_system_executor/query__static/overload1.html
doc/html/boost_asio/reference/basic_system_executor/require/overload2.html
doc/html/boost_asio/reference/basic_system_executor/require/overload7.html
doc/html/boost_asio/reference/basic_system_executor/require/overload6.html
doc/html/boost_asio/reference/basic_system_executor/require/overload4.html
doc/html/boost_asio/reference/basic_system_executor/require/overload3.html
doc/html/boost_asio/reference/basic_system_executor/require/overload5.html
doc/html/boost_asio/reference/basic_system_executor/require/overload1.html
doc/html/boost_asio/reference/streambuf.html
doc/html/boost_asio/reference/windows__basic_object_handle/close/overload2.html
doc/html/boost_asio/reference/windows__basic_object_handle/close/overload1.html
doc/html/boost_asio/reference/windows__basic_object_handle/cancel/overload2.html
doc/html/boost_asio/reference/windows__basic_object_handle/cancel/overload1.html
doc/html/boost_asio/reference/basic_signal_set.html
doc/html/boost_asio/reference/ResolveHandler.html
doc/html/boost_asio/reference/CancellationHandler.html
doc/html/boost_asio/reference/posix__basic_stream_descriptor/close/overload2.html
doc/html/boost_asio/reference/posix__basic_stream_descriptor/close/overload1.html
doc/html/boost_asio/reference/posix__basic_stream_descriptor/async_read_some.html
doc/html/boost_asio/reference/posix__basic_stream_descriptor/read_some/overload1.html
doc/html/boost_asio/reference/posix__basic_stream_descriptor/native_non_blocking/overload2.html
doc/html/boost_asio/reference/posix__basic_stream_descriptor/native_non_blocking/overload3.html
doc/html/boost_asio/reference/posix__basic_stream_descriptor/native_non_blocking/overload1.html
doc/html/boost_asio/reference/posix__basic_stream_descriptor/release.html
doc/html/boost_asio/reference/posix__basic_stream_descriptor/bytes_readable.html
doc/html/boost_asio/reference/posix__basic_stream_descriptor/cancel/overload2.html
doc/html/boost_asio/reference/posix__basic_stream_descriptor/cancel/overload1.html
doc/html/boost_asio/reference/posix__basic_stream_descriptor/async_write_some.html
doc/html/boost_asio/reference/posix__basic_stream_descriptor/write_some/overload1.html
doc/html/boost_asio/reference/posix__basic_stream_descriptor/wait/overload2.html
doc/html/boost_asio/reference/posix__basic_stream_descriptor/wait/overload1.html
doc/html/boost_asio/reference/posix__basic_stream_descriptor/async_wait.html
doc/html/boost_asio/reference/posix__basic_stream_descriptor/non_blocking/overload2.html
doc/html/boost_asio/reference/posix__basic_stream_descriptor/non_blocking/overload3.html
doc/html/boost_asio/reference/posix__basic_stream_descriptor/non_blocking/overload1.html
doc/html/boost_asio/reference/posix__basic_stream_descriptor/io_control/overload2.html
doc/html/boost_asio/reference/posix__basic_stream_descriptor/io_control/overload1.html
doc/html/boost_asio/reference/steady_timer.html
doc/html/boost_asio/reference/async_connect/overload2.html
doc/html/boost_asio/reference/async_connect/overload6.html
doc/html/boost_asio/reference/async_connect/overload4.html
doc/html/boost_asio/reference/async_connect/overload3.html
doc/html/boost_asio/reference/async_connect/overload5.html
doc/html/boost_asio/reference/async_connect/overload1.html
doc/html/boost_asio/reference/is_error_code_enum_lt__ssl_errors__gt_/value.html
doc/html/boost_asio/reference/async_completion/completion_handler_type.html
doc/html/boost_asio/reference/basic_streambuf.html
doc/html/boost_asio/reference/BufferedHandshakeHandler.html
doc/html/boost_asio/reference/thread_pool/add_service.html
doc/html/boost_asio/reference/thread_pool/make_service.html
doc/html/boost_asio/reference/windows__basic_overlapped_handle/close/overload2.html
doc/html/boost_asio/reference/windows__basic_overlapped_handle/close/overload1.html
doc/html/boost_asio/reference/windows__basic_overlapped_handle/cancel/overload2.html
doc/html/boost_asio/reference/windows__basic_overlapped_handle/cancel/overload1.html
doc/html/boost_asio/reference/require.html
doc/html/boost_asio/reference/experimental__deferred_t.html
doc/html/boost_asio/reference/io_context__service/service.html
doc/html/boost_asio/reference/io_context__service/get_io_context.html
doc/html/boost_asio/reference/static_thread_pool.html
doc/html/boost_asio/reference/SignalHandler.html
doc/html/boost_asio/reference/ip__v6_only.html
doc/html/boost_asio/reference/basic_socket_iostream/expires_from_now/overload2.html
doc/html/boost_asio/reference/basic_socket_iostream/expires_at/overload2.html
doc/html/boost_asio/reference/basic_socket_iostream/expires_after.html
doc/html/boost_asio/reference/can_query.html
doc/html/boost_asio/reference/ShutdownHandler.html
doc/html/boost_asio/reference/cancellation_state/cancellation_state/overload4.html
doc/html/boost_asio/reference/cancellation_state/cancellation_state/overload3.html
doc/html/boost_asio/reference/detached_t__executor_with_default/default_completion_token_type.html
doc/html/boost_asio/reference/execution__any_executor/prefer.html
doc/html/boost_asio/reference/execution__any_executor/require.html
doc/html/boost_asio/reference/execution__any_executor/query.html
doc/html/boost_asio/reference/buffer_copy.html
doc/html/boost_asio/reference/basic_waitable_timer__rebind_executor/other.html
doc/html/boost_asio/reference/WaitHandler.html
doc/html/boost_asio/reference/error__ssl_category.html
doc/html/boost_asio/reference/buffer_size.html
doc/html/boost_asio/reference/posix__basic_descriptor/close/overload2.html
doc/html/boost_asio/reference/posix__basic_descriptor/close/overload1.html
doc/html/boost_asio/reference/posix__basic_descriptor/native_non_blocking/overload2.html
doc/html/boost_asio/reference/posix__basic_descriptor/native_non_blocking/overload3.html
doc/html/boost_asio/reference/posix__basic_descriptor/native_non_blocking/overload1.html
doc/html/boost_asio/reference/posix__basic_descriptor/release.html
doc/html/boost_asio/reference/posix__basic_descriptor/bytes_readable.html
doc/html/boost_asio/reference/posix__basic_descriptor/cancel/overload2.html
doc/html/boost_asio/reference/posix__basic_descriptor/cancel/overload1.html
doc/html/boost_asio/reference/posix__basic_descriptor/wait/overload2.html
doc/html/boost_asio/reference/posix__basic_descriptor/wait/overload1.html
doc/html/boost_asio/reference/posix__basic_descriptor/async_wait.html
doc/html/boost_asio/reference/posix__basic_descriptor/non_blocking/overload2.html
doc/html/boost_asio/reference/posix__basic_descriptor/non_blocking/overload3.html
doc/html/boost_asio/reference/posix__basic_descriptor/non_blocking/overload1.html
doc/html/boost_asio/reference/posix__basic_descriptor/io_control/overload2.html
doc/html/boost_asio/reference/posix__basic_descriptor/io_control/overload1.html
doc/html/boost_asio/reference/dynamic_vector_buffer/const_buffers_type.html
doc/html/boost_asio/reference/dynamic_vector_buffer/mutable_buffers_type.html
doc/html/boost_asio/reference/any_io_executor/prefer/overload7.html
doc/html/boost_asio/reference/any_io_executor/prefer/overload1.html
doc/html/boost_asio/reference/any_io_executor/query.html
doc/html/boost_asio/reference/any_io_executor/require/overload3.html
doc/html/boost_asio/reference/any_io_executor/require/overload1.html
doc/html/boost_asio/reference/ip__address/to_v6.html
doc/html/boost_asio/reference/ip__address/address/overload2.html
doc/html/boost_asio/reference/ip__address/address/overload3.html
doc/html/boost_asio/reference/ip__address/address.html
doc/html/boost_asio/reference/ip__address/to_v4.html
doc/html/boost_asio/reference/ip__address/operator_eq_.html
doc/html/boost_asio/reference/ip__address/operator_eq_/overload2.html
doc/html/boost_asio/reference/ip__address/operator_eq_/overload3.html
doc/html/boost_asio/reference/HandshakeHandler.html
doc/html/boost_asio/reference/basic_random_access_file/close/overload2.html
doc/html/boost_asio/reference/basic_random_access_file/close/overload1.html
doc/html/boost_asio/reference/basic_random_access_file/read_some_at/overload1.html
doc/html/boost_asio/reference/basic_random_access_file/release/overload2.html
doc/html/boost_asio/reference/basic_random_access_file/release/overload1.html
doc/html/boost_asio/reference/basic_random_access_file/async_read_some_at.html
doc/html/boost_asio/reference/basic_random_access_file/cancel/overload2.html
doc/html/boost_asio/reference/basic_random_access_file/cancel/overload1.html
doc/html/boost_asio/reference/basic_random_access_file/async_write_some_at.html
doc/html/boost_asio/reference/basic_random_access_file/write_some_at/overload1.html
doc/html/boost_asio/reference/basic_random_access_file/open/overload2.html
doc/html/boost_asio/reference/basic_random_access_file/open/overload4.html
doc/html/boost_asio/reference/basic_random_access_file/open/overload3.html
doc/html/boost_asio/reference/basic_random_access_file/open/overload1.html
doc/html/boost_asio/reference/const_buffer.html
doc/html/boost_asio/reference/basic_waitable_timer/cancel_one/overload2.html
doc/html/boost_asio/reference/basic_waitable_timer/cancel_one/overload1.html
doc/html/boost_asio/reference/basic_waitable_timer/cancel/overload2.html
doc/html/boost_asio/reference/basic_waitable_timer/cancel/overload1.html
doc/html/boost_asio/reference/basic_waitable_timer/expires_from_now/overload2.html
doc/html/boost_asio/reference/basic_waitable_timer/expires_from_now/overload3.html
doc/html/boost_asio/reference/basic_waitable_timer/async_wait.html
doc/html/boost_asio/reference/basic_waitable_timer/expires_at/overload2.html
doc/html/boost_asio/reference/basic_waitable_timer/expires_at/overload3.html
doc/html/boost_asio/reference/basic_waitable_timer/expires_after.html
doc/html/boost_asio/reference/buffer.html
doc/html/boost_asio/reference/query.html
doc/html/boost_asio/reference/detached_t.html
doc/html/boost_asio/reference/this_coro__cancellation_state.html
doc/html/boost_asio/reference/is_nothrow_require.html
doc/html/boost_asio/reference/require_concept_result.html
doc/html/boost_asio/reference/thread_pool__basic_executor_type/query/overload2.html
doc/html/boost_asio/reference/thread_pool__basic_executor_type/query/overload6.html
doc/html/boost_asio/reference/thread_pool__basic_executor_type/query/overload4.html
doc/html/boost_asio/reference/thread_pool__basic_executor_type/query/overload3.html
doc/html/boost_asio/reference/thread_pool__basic_executor_type/query/overload5.html
doc/html/boost_asio/reference/thread_pool__basic_executor_type/query/overload1.html
doc/html/boost_asio/reference/thread_pool__basic_executor_type/query__static/overload2.html
doc/html/boost_asio/reference/thread_pool__basic_executor_type/query__static/overload3.html
doc/html/boost_asio/reference/thread_pool__basic_executor_type/query__static/overload1.html
doc/html/boost_asio/reference/thread_pool__basic_executor_type/require/overload2.html
doc/html/boost_asio/reference/thread_pool__basic_executor_type/require/overload7.html
doc/html/boost_asio/reference/thread_pool__basic_executor_type/require/overload6.html
doc/html/boost_asio/reference/thread_pool__basic_executor_type/require/overload4.html
doc/html/boost_asio/reference/thread_pool__basic_executor_type/require/overload9.html
doc/html/boost_asio/reference/thread_pool__basic_executor_type/require/overload3.html
doc/html/boost_asio/reference/thread_pool__basic_executor_type/require/overload8.html
doc/html/boost_asio/reference/thread_pool__basic_executor_type/require/overload5.html
doc/html/boost_asio/reference/thread_pool__basic_executor_type/require/overload1.html
doc/html/boost_asio/reference/null_buffers/value_type.html
doc/html/boost_asio/reference/spawn.html
doc/html/boost_asio/reference/make_strand.html
doc/html/boost_asio/reference/ssl__error__stream_category.html
doc/html/boost_asio/reference/placeholders__results.html
doc/html/boost_asio/reference/is_error_code_enum_lt__netdb_errors__gt_.html
doc/html/boost_asio/reference/ip__multicast__outbound_interface.html
doc/html/boost_asio/reference/basic_streambuf_ref/const_buffers_type.html
doc/html/boost_asio/reference/basic_streambuf_ref/mutable_buffers_type.html
doc/html/boost_asio/reference/basic_writable_pipe/close/overload2.html
doc/html/boost_asio/reference/basic_writable_pipe/close/overload1.html
doc/html/boost_asio/reference/basic_writable_pipe/cancel/overload2.html
doc/html/boost_asio/reference/basic_writable_pipe/cancel/overload1.html
doc/html/boost_asio/reference/basic_writable_pipe/async_write_some.html
doc/html/boost_asio/reference/basic_writable_pipe/write_some/overload1.html
doc/html/boost_asio/reference/is_nothrow_query.html
doc/html/boost_asio/reference/ip__multicast__hops.html
doc/html/boost_asio/reference/ConnectHandler.html
doc/html/boost_asio/reference/ip__tcp/acceptor.html
doc/html/boost_asio/reference/ip__tcp/no_delay.html
doc/html/boost_asio/reference/AcceptHandler.html
doc/html/boost_asio/reference/this_coro__reset_cancellation_state/overload2.html
doc/html/boost_asio/reference/this_coro__reset_cancellation_state/overload3.html
doc/html/boost_asio/reference/this_coro__reset_cancellation_state/overload1.html
doc/html/boost_asio/reference/buffer_cast.html
doc/html/boost_asio/reference/can_require_concept.html
doc/html/boost_asio/reference/ssl__stream/native_handle.html
doc/html/boost_asio/reference/is_error_code_enum_lt__addrinfo_errors__gt_.html
doc/html/boost_asio/reference/prefer_result.html
doc/html/boost_asio/reference/is_error_code_enum_lt__boost__asio__experimental__error__channel_errors__gt_.html
doc/html/boost_asio/reference/basic_io_object/executor_type.html
doc/html/boost_asio/reference/basic_io_object/basic_io_object.html
doc/html/boost_asio/reference/basic_io_object/get_io_context.html
doc/html/boost_asio/reference/basic_io_object/get_io_service.html
doc/html/boost_asio/reference/basic_io_object/basic_io_object/overload1.html
doc/html/boost_asio/reference/generic__stream_protocol.html
doc/html/boost_asio/reference/ip__multicast__join_group.html
doc/html/boost_asio/reference/ssl__rfc2818_verification.html
doc/html/boost_asio/reference/io_context__basic_executor_type/query/overload2.html
doc/html/boost_asio/reference/io_context__basic_executor_type/query/overload4.html
doc/html/boost_asio/reference/io_context__basic_executor_type/query/overload3.html
doc/html/boost_asio/reference/io_context__basic_executor_type/query/overload5.html
doc/html/boost_asio/reference/io_context__basic_executor_type/query/overload1.html
doc/html/boost_asio/reference/io_context__basic_executor_type/query__static/overload2.html
doc/html/boost_asio/reference/io_context__basic_executor_type/query__static/overload1.html
doc/html/boost_asio/reference/io_context__basic_executor_type/require/overload2.html
doc/html/boost_asio/reference/io_context__basic_executor_type/require/overload7.html
doc/html/boost_asio/reference/io_context__basic_executor_type/require/overload6.html
doc/html/boost_asio/reference/io_context__basic_executor_type/require/overload4.html
doc/html/boost_asio/reference/io_context__basic_executor_type/require/overload3.html
doc/html/boost_asio/reference/io_context__basic_executor_type/require/overload8.html
doc/html/boost_asio/reference/io_context__basic_executor_type/require/overload5.html
doc/html/boost_asio/reference/io_context__basic_executor_type/require/overload1.html
doc/html/boost_asio/reference/basic_socket_acceptor.html
doc/html/boost_asio/reference/system_timer.html
doc/html/boost_asio/reference/read_at/overload2.html
doc/html/boost_asio/reference/read_at/overload6.html
doc/html/boost_asio/reference/read_at/overload3.html
doc/html/boost_asio/reference/read_at/overload5.html
doc/html/boost_asio/reference/read_at/overload1.html
doc/html/boost_asio/reference/async_write/overload2.html
doc/html/boost_asio/reference/async_write/overload1.html
doc/html/boost_asio/reference/is_error_code_enum_lt__boost__asio__experimental__error__channel_errors__gt_/value.html
doc/html/boost_asio/reference/connect/overload2.html
doc/html/boost_asio/reference/connect/overload7.html
doc/html/boost_asio/reference/connect/overload6.html
doc/html/boost_asio/reference/connect/overload4.html
doc/html/boost_asio/reference/connect/overload9.html
doc/html/boost_asio/reference/connect/overload10.html
doc/html/boost_asio/reference/connect/overload3.html
doc/html/boost_asio/reference/connect/overload12.html
doc/html/boost_asio/reference/connect/overload8.html
doc/html/boost_asio/reference/connect/overload11.html
doc/html/boost_asio/reference/connect/overload5.html
doc/html/boost_asio/reference/connect/overload1.html
doc/html/boost_asio/reference/windows__basic_random_access_handle/close/overload2.html
doc/html/boost_asio/reference/windows__basic_random_access_handle/close/overload1.html
doc/html/boost_asio/reference/windows__basic_random_access_handle/read_some_at/overload1.html
doc/html/boost_asio/reference/windows__basic_random_access_handle/async_read_some_at.html
doc/html/boost_asio/reference/windows__basic_random_access_handle/cancel/overload2.html
doc/html/boost_asio/reference/windows__basic_random_access_handle/cancel/overload1.html
doc/html/boost_asio/reference/windows__basic_random_access_handle/async_write_some_at.html
doc/html/boost_asio/reference/windows__basic_random_access_handle/write_some_at/overload1.html
doc/html/boost_asio/reference/write_at/overload2.html
doc/html/boost_asio/reference/write_at/overload6.html
doc/html/boost_asio/reference/write_at/overload3.html
doc/html/boost_asio/reference/write_at/overload5.html
doc/html/boost_asio/reference/write_at/overload1.html
doc/html/boost_asio/reference/read_until/overload19.html
doc/html/boost_asio/reference/read_until/overload21.html
doc/html/boost_asio/reference/read_until/overload23.html
doc/html/boost_asio/reference/read_until/overload7.html
doc/html/boost_asio/reference/read_until/overload13.html
doc/html/boost_asio/reference/read_until/overload9.html
doc/html/boost_asio/reference/read_until/overload10.html
doc/html/boost_asio/reference/read_until/overload3.html
doc/html/boost_asio/reference/read_until/overload12.html
doc/html/boost_asio/reference/read_until/overload17.html
doc/html/boost_asio/reference/read_until/overload16.html
doc/html/boost_asio/reference/read_until/overload15.html
doc/html/boost_asio/reference/read_until/overload14.html
doc/html/boost_asio/reference/read_until/overload11.html
doc/html/boost_asio/reference/read_until/overload5.html
doc/html/boost_asio/reference/read_until/overload1.html
doc/html/boost_asio/reference/ip__unicast__hops.html
doc/html/boost_asio/reference/error__system_category.html
doc/html/boost_asio/reference/dynamic_string_buffer/const_buffers_type.html
doc/html/boost_asio/reference/dynamic_string_buffer/mutable_buffers_type.html
doc/html/boost_asio/reference/Handler.html
doc/html/boost_asio/reference/MutableBufferSequence.html
doc/html/boost_asio/reference/mutable_buffers_1/value_type.html
doc/html/boost_asio/reference/strand/prefer.html
doc/html/boost_asio/reference/strand/require.html
doc/html/boost_asio/reference/strand/execute.html
doc/html/boost_asio/reference/strand/query.html
doc/html/boost_asio/reference/is_nothrow_prefer.html
doc/html/boost_asio/reference/basic_raw_socket/send_buffer_size.html
doc/html/boost_asio/reference/basic_raw_socket/get_option/overload2.html
doc/html/boost_asio/reference/basic_raw_socket/get_option/overload1.html
doc/html/boost_asio/reference/basic_raw_socket/close/overload2.html
doc/html/boost_asio/reference/basic_raw_socket/close/overload1.html
doc/html/boost_asio/reference/basic_raw_socket/async_send_to/overload1.html
doc/html/boost_asio/reference/basic_raw_socket/linger.html
doc/html/boost_asio/reference/basic_raw_socket/debug.html
doc/html/boost_asio/reference/basic_raw_socket/receive_low_watermark.html
doc/html/boost_asio/reference/basic_raw_socket/do_not_route.html
doc/html/boost_asio/reference/basic_raw_socket/native_non_blocking/overload2.html
doc/html/boost_asio/reference/basic_raw_socket/native_non_blocking/overload3.html
doc/html/boost_asio/reference/basic_raw_socket/native_non_blocking/overload1.html
doc/html/boost_asio/reference/basic_raw_socket/async_send/overload1.html
doc/html/boost_asio/reference/basic_raw_socket/release/overload2.html
doc/html/boost_asio/reference/basic_raw_socket/release/overload1.html
doc/html/boost_asio/reference/basic_raw_socket/async_connect.html
doc/html/boost_asio/reference/basic_raw_socket/async_receive/overload1.html
doc/html/boost_asio/reference/basic_raw_socket/bytes_readable.html
doc/html/boost_asio/reference/basic_raw_socket/cancel/overload2.html
doc/html/boost_asio/reference/basic_raw_socket/cancel/overload1.html
doc/html/boost_asio/reference/basic_raw_socket/enable_connection_aborted.html
doc/html/boost_asio/reference/basic_raw_socket/send_to/overload1.html
doc/html/boost_asio/reference/basic_raw_socket/local_endpoint/overload2.html
doc/html/boost_asio/reference/basic_raw_socket/local_endpoint/overload1.html
doc/html/boost_asio/reference/basic_raw_socket/receive/overload1.html
doc/html/boost_asio/reference/basic_raw_socket/send_low_watermark.html
doc/html/boost_asio/reference/basic_raw_socket/keep_alive.html
doc/html/boost_asio/reference/basic_raw_socket/wait/overload2.html
doc/html/boost_asio/reference/basic_raw_socket/wait/overload1.html
doc/html/boost_asio/reference/basic_raw_socket/receive_from/overload1.html
doc/html/boost_asio/reference/basic_raw_socket/open/overload2.html
doc/html/boost_asio/reference/basic_raw_socket/open/overload1.html
doc/html/boost_asio/reference/basic_raw_socket/async_wait.html
doc/html/boost_asio/reference/basic_raw_socket/set_option/overload2.html
doc/html/boost_asio/reference/basic_raw_socket/set_option/overload1.html
doc/html/boost_asio/reference/basic_raw_socket/non_blocking/overload2.html
doc/html/boost_asio/reference/basic_raw_socket/non_blocking/overload3.html
doc/html/boost_asio/reference/basic_raw_socket/non_blocking/overload1.html
doc/html/boost_asio/reference/basic_raw_socket/broadcast.html
doc/html/boost_asio/reference/basic_raw_socket/shutdown/overload2.html
doc/html/boost_asio/reference/basic_raw_socket/shutdown/overload1.html
doc/html/boost_asio/reference/basic_raw_socket/remote_endpoint/overload2.html
doc/html/boost_asio/reference/basic_raw_socket/remote_endpoint/overload1.html
doc/html/boost_asio/reference/basic_raw_socket/out_of_band_inline.html
doc/html/boost_asio/reference/basic_raw_socket/connect/overload2.html
doc/html/boost_asio/reference/basic_raw_socket/connect/overload1.html
doc/html/boost_asio/reference/basic_raw_socket/io_control/overload2.html
doc/html/boost_asio/reference/basic_raw_socket/io_control/overload1.html
doc/html/boost_asio/reference/basic_raw_socket/bind/overload2.html
doc/html/boost_asio/reference/basic_raw_socket/bind/overload1.html
doc/html/boost_asio/reference/basic_raw_socket/receive_buffer_size.html
doc/html/boost_asio/reference/basic_raw_socket/send/overload1.html
doc/html/boost_asio/reference/basic_raw_socket/reuse_address.html
doc/html/boost_asio/reference/basic_raw_socket/async_receive_from/overload1.html
doc/html/boost_asio/reference/basic_readable_pipe/close/overload2.html
doc/html/boost_asio/reference/basic_readable_pipe/close/overload1.html
doc/html/boost_asio/reference/basic_readable_pipe/async_read_some.html
doc/html/boost_asio/reference/basic_readable_pipe/read_some/overload1.html
doc/html/boost_asio/reference/basic_readable_pipe/cancel/overload2.html
doc/html/boost_asio/reference/basic_readable_pipe/cancel/overload1.html
doc/html/boost_asio/reference/Executor1.html
doc/html/boost_asio/reference/basic_signal_set/cancel/overload2.html
doc/html/boost_asio/reference/basic_signal_set/cancel/overload1.html
doc/html/boost_asio/reference/basic_signal_set/async_wait.html
doc/html/boost_asio/reference/basic_signal_set/basic_signal_set/overload7.html
doc/html/boost_asio/reference/basic_signal_set/basic_signal_set/overload6.html
doc/html/boost_asio/reference/basic_signal_set/basic_signal_set/overload4.html
doc/html/boost_asio/reference/basic_signal_set/basic_signal_set/overload3.html
doc/html/boost_asio/reference/basic_signal_set/basic_signal_set/overload8.html
doc/html/boost_asio/reference/basic_signal_set/basic_signal_set/overload5.html
doc/html/boost_asio/reference/buffer_sequence_begin.html
doc/html/boost_asio/reference/basic_stream_file/close/overload2.html
doc/html/boost_asio/reference/basic_stream_file/close/overload1.html
doc/html/boost_asio/reference/basic_stream_file/async_read_some.html
doc/html/boost_asio/reference/basic_stream_file/read_some/overload1.html
doc/html/boost_asio/reference/basic_stream_file/release/overload2.html
doc/html/boost_asio/reference/basic_stream_file/release/overload1.html
doc/html/boost_asio/reference/basic_stream_file/cancel/overload2.html
doc/html/boost_asio/reference/basic_stream_file/cancel/overload1.html
doc/html/boost_asio/reference/basic_stream_file/async_write_some.html
doc/html/boost_asio/reference/basic_stream_file/write_some/overload1.html
doc/html/boost_asio/reference/basic_stream_file/open/overload2.html
doc/html/boost_asio/reference/basic_stream_file/open/overload4.html
doc/html/boost_asio/reference/basic_stream_file/open/overload3.html
doc/html/boost_asio/reference/basic_stream_file/open/overload1.html
doc/html/boost_asio/reference/transfer_exactly.html
doc/html/boost_asio/reference/cancellation_slot/assign.html
doc/html/boost_asio/reference/cancellation_slot/emplace.html
doc/html/boost_asio/reference/ip__basic_resolver_query/hints.html
doc/html/boost_asio/reference/local__stream_protocol/acceptor.html
doc/html/boost_asio/reference/require_concept.html
doc/html/boost_asio/reference/basic_file/close/overload2.html
doc/html/boost_asio/reference/basic_file/close/overload1.html
doc/html/boost_asio/reference/basic_file/release/overload2.html
doc/html/boost_asio/reference/basic_file/release/overload1.html
doc/html/boost_asio/reference/basic_file/cancel/overload2.html
doc/html/boost_asio/reference/basic_file/cancel/overload1.html
doc/html/boost_asio/reference/basic_file/open/overload2.html
doc/html/boost_asio/reference/basic_file/open/overload4.html
doc/html/boost_asio/reference/basic_file/open/overload3.html
doc/html/boost_asio/reference/basic_file/open/overload1.html
doc/html/boost_asio/reference/read/overload2.html
doc/html/boost_asio/reference/read/overload6.html
doc/html/boost_asio/reference/read/overload13.html
doc/html/boost_asio/reference/read/overload9.html
doc/html/boost_asio/reference/read/overload10.html
doc/html/boost_asio/reference/read/overload3.html
doc/html/boost_asio/reference/read/overload14.html
doc/html/boost_asio/reference/read/overload5.html
doc/html/boost_asio/reference/read/overload1.html
doc/html/boost_asio/reference/is_error_code_enum_lt__basic_errors__gt_/value.html
doc/html/boost_asio/reference/experimental__make_parallel_group.html
doc/html/boost_asio/reference/io_context/add_service.html
doc/html/boost_asio/reference/io_context/make_service.html
doc/html/boost_asio/reference/async_compose.html
doc/html/boost_asio/reference/is_error_code_enum_lt__ssl_errors__gt_.html
doc/html/boost_asio/reference/write/overload2.html
doc/html/boost_asio/reference/write/overload6.html
doc/html/boost_asio/reference/write/overload13.html
doc/html/boost_asio/reference/write/overload9.html
doc/html/boost_asio/reference/write/overload10.html
doc/html/boost_asio/reference/write/overload3.html
doc/html/boost_asio/reference/write/overload14.html
doc/html/boost_asio/reference/write/overload5.html
doc/html/boost_asio/reference/write/overload1.html
doc/html/boost_asio/reference/execution__bulk_execute.html
doc/html/boost_asio/reference/high_resolution_timer.html
doc/html/boost_asio/reference/placeholders__signal_number.html
doc/html/boost_asio/reference/basic_deadline_timer.html
doc/html/boost_asio/net_ts.html
doc/html/boost_asio/history.html
doc/html/boost_asio/example/cpp17/coroutines_ts/echo_server_with_default.cpp
doc/html/boost_asio/example/cpp17/coroutines_ts/refactored_echo_server.cpp
doc/html/boost_asio/example/cpp17/coroutines_ts/chat_server.cpp
doc/html/boost_asio/example/cpp17/coroutines_ts/echo_server.cpp
doc/html/boost_asio/example/cpp17/coroutines_ts/range_based_for.cpp
doc/html/boost_asio/example/cpp17/coroutines_ts/echo_server_with_as_tuple_default.cpp
doc/html/boost_asio/example/cpp17/coroutines_ts/echo_server_with_as_single_default.cpp
doc/html/boost_asio/example/cpp20/channels/throttling_proxy.cpp
doc/html/boost_asio/example/cpp11/allocation/server.cpp
doc/html/boost_asio/example/cpp11/timers/time_t_timer.cpp
doc/html/boost_asio/example/cpp11/nonblocking/third_party_lib.cpp
doc/html/boost_asio/example/cpp11/executors/fork_join.cpp
doc/html/boost_asio/example/cpp11/executors/bank_account_1.cpp
doc/html/boost_asio/example/cpp11/executors/bank_account_2.cpp
doc/html/boost_asio/example/cpp11/executors/actor.cpp
doc/html/boost_asio/example/cpp11/executors/priority_scheduler.cpp
doc/html/boost_asio/example/cpp11/executors/pipeline.cpp
doc/html/boost_asio/example/cpp11/invocation/prioritised_handlers.cpp
doc/html/boost_asio/example/cpp11/spawn/parallel_grep.cpp
doc/html/boost_asio/example/cpp11/spawn/echo_server.cpp
doc/html/boost_asio/example/cpp11/socks4/sync_client.cpp
doc/html/boost_asio/example/cpp11/socks4/socks4.hpp
doc/html/boost_asio/example/cpp11/operations/composed_4.cpp
doc/html/boost_asio/example/cpp11/operations/composed_1.cpp
doc/html/boost_asio/example/cpp11/operations/composed_2.cpp
doc/html/boost_asio/example/cpp11/operations/composed_3.cpp
doc/html/boost_asio/example/cpp11/operations/composed_8.cpp
doc/html/boost_asio/example/cpp11/operations/composed_5.cpp
doc/html/boost_asio/example/cpp11/operations/composed_7.cpp
doc/html/boost_asio/example/cpp11/operations/composed_6.cpp
doc/html/boost_asio/example/cpp11/local/iostream_client.cpp
doc/html/boost_asio/example/cpp11/local/connect_pair.cpp
doc/html/boost_asio/example/cpp11/local/stream_server.cpp
doc/html/boost_asio/example/cpp11/local/stream_client.cpp
doc/html/boost_asio/example/cpp11/multicast/sender.cpp
doc/html/boost_asio/example/cpp11/multicast/receiver.cpp
doc/html/boost_asio/example/cpp11/handler_tracking/custom_tracking.hpp
doc/html/boost_asio/example/cpp11/handler_tracking/async_tcp_echo_server.cpp
doc/html/boost_asio/example/cpp11/timeouts/blocking_udp_client.cpp
doc/html/boost_asio/example/cpp11/timeouts/async_tcp_client.cpp
doc/html/boost_asio/example/cpp11/timeouts/blocking_tcp_client.cpp
doc/html/boost_asio/example/cpp11/timeouts/server.cpp
doc/html/boost_asio/example/cpp11/timeouts/blocking_token_tcp_client.cpp
doc/html/boost_asio/example/cpp11/chat/chat_server.cpp
doc/html/boost_asio/example/cpp11/chat/chat_client.cpp
doc/html/boost_asio/example/cpp11/futures/daytime_client.cpp
doc/html/boost_asio/example/cpp11/echo/blocking_udp_echo_client.cpp
doc/html/boost_asio/example/cpp11/echo/async_udp_echo_server.cpp
doc/html/boost_asio/example/cpp11/echo/blocking_tcp_echo_server.cpp
doc/html/boost_asio/example/cpp11/echo/async_tcp_echo_server.cpp
doc/html/boost_asio/example/cpp11/echo/blocking_tcp_echo_client.cpp
doc/html/boost_asio/example/cpp11/echo/blocking_udp_echo_server.cpp
doc/html/boost_asio/example/cpp11/buffers/reference_counted.cpp
doc/html/boost_asio/example/cpp11/fork/process_per_connection.cpp
doc/html/boost_asio/example/cpp11/fork/daemon.cpp
doc/html/boost_asio/example/cpp11/http/server/reply.hpp
doc/html/boost_asio/example/cpp11/http/server/server.cpp
doc/html/boost_asio/example/cpp11/http/server/reply.cpp
doc/html/boost_asio/example/cpp11/http/server/server.hpp
doc/html/boost_asio/example/cpp11/http/server/connection.hpp
doc/html/boost_asio/example/cpp11/http/server/connection.cpp
doc/html/boost_asio/example/cpp11/ssl/client.cpp
doc/html/boost_asio/example/cpp11/ssl/server.cpp
doc/html/boost_asio/example/cpp03/allocation/server.cpp
doc/html/boost_asio/example/cpp03/timers/time_t_timer.cpp
doc/html/boost_asio/example/cpp03/nonblocking/third_party_lib.cpp
doc/html/boost_asio/example/cpp03/services/basic_logger.hpp
doc/html/boost_asio/example/cpp03/services/daytime_client.cpp
doc/html/boost_asio/example/cpp03/services/logger_service.hpp
doc/html/boost_asio/example/cpp03/windows/transmit_file.cpp
doc/html/boost_asio/example/cpp03/invocation/prioritised_handlers.cpp
doc/html/boost_asio/example/cpp03/serialization/client.cpp
doc/html/boost_asio/example/cpp03/serialization/server.cpp
doc/html/boost_asio/example/cpp03/serialization/connection.hpp
doc/html/boost_asio/example/cpp03/spawn/parallel_grep.cpp
doc/html/boost_asio/example/cpp03/spawn/echo_server.cpp
doc/html/boost_asio/example/cpp03/socks4/sync_client.cpp
doc/html/boost_asio/example/cpp03/socks4/socks4.hpp
doc/html/boost_asio/example/cpp03/porthopper/protocol.hpp
doc/html/boost_asio/example/cpp03/porthopper/client.cpp
doc/html/boost_asio/example/cpp03/porthopper/server.cpp
doc/html/boost_asio/example/cpp03/iostreams/daytime_server.cpp
doc/html/boost_asio/example/cpp03/iostreams/http_client.cpp
doc/html/boost_asio/example/cpp03/iostreams/daytime_client.cpp
doc/html/boost_asio/example/cpp03/local/iostream_client.cpp
doc/html/boost_asio/example/cpp03/local/connect_pair.cpp
doc/html/boost_asio/example/cpp03/local/stream_server.cpp
doc/html/boost_asio/example/cpp03/local/stream_client.cpp
doc/html/boost_asio/example/cpp03/multicast/sender.cpp
doc/html/boost_asio/example/cpp03/multicast/receiver.cpp
doc/html/boost_asio/example/cpp03/timeouts/blocking_udp_client.cpp
doc/html/boost_asio/example/cpp03/timeouts/async_tcp_client.cpp
doc/html/boost_asio/example/cpp03/timeouts/blocking_tcp_client.cpp
doc/html/boost_asio/example/cpp03/timeouts/server.cpp
doc/html/boost_asio/example/cpp03/timeouts/blocking_token_tcp_client.cpp
doc/html/boost_asio/example/cpp03/chat/chat_server.cpp
doc/html/boost_asio/example/cpp03/chat/chat_client.cpp
doc/html/boost_asio/example/cpp03/chat/posix_chat_client.cpp
doc/html/boost_asio/example/cpp03/echo/blocking_udp_echo_client.cpp
doc/html/boost_asio/example/cpp03/echo/async_udp_echo_server.cpp
doc/html/boost_asio/example/cpp03/echo/blocking_tcp_echo_server.cpp
doc/html/boost_asio/example/cpp03/echo/async_tcp_echo_server.cpp
doc/html/boost_asio/example/cpp03/echo/blocking_tcp_echo_client.cpp
doc/html/boost_asio/example/cpp03/echo/blocking_udp_echo_server.cpp
doc/html/boost_asio/example/cpp03/buffers/reference_counted.cpp
doc/html/boost_asio/example/cpp03/fork/process_per_connection.cpp
doc/html/boost_asio/example/cpp03/fork/daemon.cpp
doc/html/boost_asio/example/cpp03/http/server2/io_context_pool.hpp
doc/html/boost_asio/example/cpp03/http/server2/io_context_pool.cpp
doc/html/boost_asio/example/cpp03/http/server2/reply.hpp
doc/html/boost_asio/example/cpp03/http/server2/server.cpp
doc/html/boost_asio/example/cpp03/http/server2/reply.cpp
doc/html/boost_asio/example/cpp03/http/server2/server.hpp
doc/html/boost_asio/example/cpp03/http/server2/connection.hpp
doc/html/boost_asio/example/cpp03/http/server2/connection.cpp
doc/html/boost_asio/example/cpp03/http/server4/request_parser.hpp
doc/html/boost_asio/example/cpp03/http/server4/reply.hpp
doc/html/boost_asio/example/cpp03/http/server4/server.cpp
doc/html/boost_asio/example/cpp03/http/server4/reply.cpp
doc/html/boost_asio/example/cpp03/http/server4/main.cpp
doc/html/boost_asio/example/cpp03/http/server4/server.hpp
doc/html/boost_asio/example/cpp03/http/server/reply.hpp
doc/html/boost_asio/example/cpp03/http/server/server.cpp
doc/html/boost_asio/example/cpp03/http/server/reply.cpp
doc/html/boost_asio/example/cpp03/http/server/server.hpp
doc/html/boost_asio/example/cpp03/http/server/connection.hpp
doc/html/boost_asio/example/cpp03/http/server/connection.cpp
doc/html/boost_asio/example/cpp03/http/client/sync_client.cpp
doc/html/boost_asio/example/cpp03/http/client/async_client.cpp
doc/html/boost_asio/example/cpp03/http/server3/reply.hpp
doc/html/boost_asio/example/cpp03/http/server3/server.cpp
doc/html/boost_asio/example/cpp03/http/server3/reply.cpp
doc/html/boost_asio/example/cpp03/http/server3/server.hpp
doc/html/boost_asio/example/cpp03/http/server3/connection.hpp
doc/html/boost_asio/example/cpp03/http/server3/connection.cpp
doc/html/boost_asio/example/cpp03/icmp/ipv4_header.hpp
doc/html/boost_asio/example/cpp03/icmp/ping.cpp
doc/html/boost_asio/example/cpp03/ssl/client.cpp
doc/html/boost_asio/example/cpp03/ssl/server.cpp
doc/html/boost_asio/example/cpp14/executors/fork_join.cpp
doc/html/boost_asio/example/cpp14/executors/bank_account_1.cpp
doc/html/boost_asio/example/cpp14/executors/bank_account_2.cpp
doc/html/boost_asio/example/cpp14/executors/actor.cpp
doc/html/boost_asio/example/cpp14/executors/priority_scheduler.cpp
doc/html/boost_asio/example/cpp14/executors/async_2.cpp
doc/html/boost_asio/example/cpp14/executors/async_1.cpp
doc/html/boost_asio/example/cpp14/executors/pipeline.cpp
doc/html/boost_asio/example/cpp14/deferred/deferred_1.cpp
doc/html/boost_asio/example/cpp14/deferred/deferred_3.cpp
doc/html/boost_asio/example/cpp14/deferred/deferred_7.cpp
doc/html/boost_asio/example/cpp14/deferred/deferred_2.cpp
doc/html/boost_asio/example/cpp14/deferred/deferred_4.cpp
doc/html/boost_asio/example/cpp14/deferred/deferred_5.cpp
doc/html/boost_asio/example/cpp14/deferred/deferred_6.cpp
doc/html/boost_asio/example/cpp14/iostreams/http_client.cpp
doc/html/boost_asio/example/cpp14/operations/composed_4.cpp
doc/html/boost_asio/example/cpp14/operations/composed_1.cpp
doc/html/boost_asio/example/cpp14/operations/composed_2.cpp
doc/html/boost_asio/example/cpp14/operations/composed_3.cpp
doc/html/boost_asio/example/cpp14/operations/composed_8.cpp
doc/html/boost_asio/example/cpp14/operations/composed_5.cpp
doc/html/boost_asio/example/cpp14/operations/composed_7.cpp
doc/html/boost_asio/example/cpp14/operations/composed_6.cpp
doc/html/boost_asio/example/cpp14/parallel_group/wait_for_one.cpp
doc/html/boost_asio/example/cpp14/parallel_group/wait_for_all.cpp
doc/html/boost_asio/example/cpp14/parallel_group/wait_for_one_error.cpp
doc/html/boost_asio/example/cpp14/parallel_group/parallel_sort.cpp
doc/html/boost_asio/example/cpp14/parallel_group/wait_for_one_success.cpp
doc/html/boost_asio/overview/signals.html
doc/html/boost_asio/overview/ssl.html
doc/html/boost_asio/overview/cpp2011/futures.html
doc/html/boost_asio/overview/cpp2011/move_handlers.html
doc/html/boost_asio/overview/core/coroutine.html
doc/html/boost_asio/overview/core/strands.html
doc/html/boost_asio/overview/core/cpp20_coroutines.html
doc/html/boost_asio/overview/core/cancellation.html
doc/html/boost_asio/overview/core/line_based.html
doc/html/boost_asio/overview/core/coro.html
doc/html/boost_asio/overview/core/spawn.html
doc/html/boost_asio/overview/core/allocation.html
doc/html/boost_asio/overview/networking/protocols.html
doc/html/boost_asio/overview/networking/other_protocols.html
doc/html/boost_asio/overview/posix/stream_descriptor.html
doc/html/boost_asio/overview/posix/fork.html
doc/html/boost_asio/examples/cpp11_examples.html
doc/html/boost_asio/examples/cpp03_examples.html
doc/html/boost/process/std_in.html
doc/html/boost/process/spawn.html
doc/html/boost/process/on_exit.html
doc/html/boost/process/async_pipe.html
doc/html/boost/process/std_out.html
doc/html/process/reference.html
doc/html/boost_process/tutorial.html
doc/html/boost_process/extend.html
libs/fiber/doc/fibers.qbk
libs/fiber/doc/integration.qbk
libs/fiber/doc/callbacks.qbk
libs/fiber/doc/asio.qbk
libs/fiber/examples/asio/round_robin.hpp
libs/fiber/examples/asio/exchange.cpp
libs/fiber/examples/asio/autoecho.cpp
libs/fiber/examples/asio/ps/server.cpp
libs/fiber/examples/asio/ps/subscriber.cpp
libs/fiber/examples/asio/ps/publisher.cpp
libs/leaf/example/asio_beast_leaf_rpc.cpp
libs/coroutine/doc/motivation.qbk
libs/coroutine/doc/coro.qbk
libs/coroutine/doc/html/coroutine/motivation.html
libs/log/doc/tmp/sinks_reference.xml
libs/log/src/syslog_backend.cpp
libs/phoenix/example/adapted_echo_server.cpp
libs/asio/doc/history.qbk
libs/asio/doc/using.qbk
libs/asio/doc/std_executors.qbk
libs/asio/doc/reference.qbk
libs/asio/doc/tutorial.qbk
libs/asio/doc/reference.xsl
libs/asio/doc/requirements/HandshakeHandler.qbk
libs/asio/doc/requirements/Scheduler.qbk
libs/asio/doc/requirements/IteratorConnectHandler.qbk
libs/asio/doc/requirements/Executor.qbk
libs/asio/doc/requirements/WriteHandler.qbk
libs/asio/doc/requirements/ShutdownHandler.qbk
libs/asio/doc/requirements/ReadHandler.qbk
libs/asio/doc/requirements/RangeConnectHandler.qbk
libs/asio/doc/requirements/ResolveHandler.qbk
libs/asio/doc/requirements/CancellationHandler.qbk
libs/asio/doc/requirements/BufferedHandshakeHandler.qbk
libs/asio/doc/requirements/ConstBufferSequence.qbk
libs/asio/doc/requirements/AcceptHandler.qbk
libs/asio/doc/requirements/ConnectHandler.qbk
libs/asio/doc/requirements/MoveAcceptHandler.qbk
libs/asio/doc/requirements/Handler.qbk
libs/asio/doc/requirements/MutableBufferSequence.qbk
libs/asio/doc/requirements/WaitHandler.qbk
libs/asio/doc/requirements/SignalHandler.qbk
libs/asio/doc/overview/handler_tracking.qbk
libs/asio/doc/overview/cancellation.qbk
libs/asio/doc/overview/line_based.qbk
libs/asio/doc/overview/coroutine.qbk
libs/asio/doc/overview/cpp20_coroutines.qbk
libs/asio/doc/overview/ssl.qbk
libs/asio/doc/overview/other_protocols.qbk
libs/asio/doc/overview/allocation.qbk
libs/asio/doc/overview/basics.qbk
libs/asio/doc/overview/protocols.qbk
libs/asio/doc/overview/spawn.qbk
libs/asio/doc/overview/cpp2011.qbk
libs/asio/doc/overview/signals.qbk
libs/asio/doc/overview/posix.qbk
libs/asio/doc/overview/strands.qbk
libs/asio/doc/overview/coro.qbk
libs/asio/doc/overview/buffers.qbk
libs/asio/doc/examples.qbk
libs/asio/test/connect_pipe.cpp
libs/asio/test/bind_executor.cpp
libs/asio/test/readable_pipe.cpp
libs/asio/test/serial_port.cpp
libs/asio/test/experimental/concurrent_channel.cpp
libs/asio/test/experimental/awaitable_operators.cpp
libs/asio/test/experimental/coro/cancel.cpp
libs/asio/test/experimental/coro/co_spawn.cpp
libs/asio/test/experimental/coro/executor.cpp
libs/asio/test/experimental/coro/partial.cpp
libs/asio/test/experimental/coro/stack_test.cpp
libs/asio/test/experimental/coro/use_coro.cpp
libs/asio/test/experimental/coro/exception.cpp
libs/asio/test/experimental/coro/simple_test.cpp
libs/asio/test/experimental/promise.cpp
libs/asio/test/experimental/channel.cpp
libs/asio/test/writable_pipe.cpp
libs/asio/test/thread_pool.cpp
libs/asio/test/windows/object_handle.cpp
libs/asio/test/windows/overlapped_ptr.cpp
libs/asio/test/windows/random_access_handle.cpp
libs/asio/test/windows/stream_handle.cpp
libs/asio/test/generic/stream_protocol.cpp
libs/asio/test/generic/seq_packet_protocol.cpp
libs/asio/test/generic/datagram_protocol.cpp
libs/asio/test/generic/raw_protocol.cpp
libs/asio/test/streambuf.cpp
libs/asio/test/connect.cpp
libs/asio/test/buffered_stream.cpp
libs/asio/test/read_until.cpp
libs/asio/test/io_context.cpp
libs/asio/test/read.cpp
libs/asio/test/ip/address_v4.cpp
libs/asio/test/ip/v6_only.cpp
libs/asio/test/ip/udp.cpp
libs/asio/test/ip/network_v4.cpp
libs/asio/test/ip/address.cpp
libs/asio/test/ip/host_name.cpp
libs/asio/test/ip/icmp.cpp
libs/asio/test/ip/multicast.cpp
libs/asio/test/ip/unicast.cpp
libs/asio/test/ip/tcp.cpp
libs/asio/test/ip/address_v6.cpp
libs/asio/test/ip/network_v6.cpp
libs/asio/test/properties/cpp11/require_concept_free.cpp
libs/asio/test/properties/cpp11/can_query_not_applicable_free.cpp
libs/asio/test/properties/cpp11/can_prefer_not_preferable_member_require.cpp
libs/asio/test/properties/cpp11/require_free.cpp
libs/asio/test/properties/cpp11/can_query_not_applicable_static.cpp
libs/asio/test/properties/cpp11/prefer_unsupported.cpp
libs/asio/test/properties/cpp11/can_prefer_unsupported.cpp
libs/asio/test/properties/cpp11/query_static.cpp
libs/asio/test/properties/cpp11/can_prefer_not_preferable_static.cpp
libs/asio/test/properties/cpp11/can_prefer_not_preferable_free_prefer.cpp
libs/asio/test/properties/cpp11/can_prefer_free_require.cpp
libs/asio/test/properties/cpp11/can_require_not_applicable_unsupported.cpp
libs/asio/test/properties/cpp11/prefer_member_prefer.cpp
libs/asio/test/properties/cpp11/require_concept_member.cpp
libs/asio/test/properties/cpp11/can_require_concept_member.cpp
libs/asio/test/properties/cpp11/can_prefer_not_applicable_member_require.cpp
libs/asio/test/properties/cpp11/can_query_member.cpp
libs/asio/test/properties/cpp11/can_prefer_not_applicable_member_prefer.cpp
libs/asio/test/properties/cpp11/can_query_free.cpp
libs/asio/test/properties/cpp11/can_require_not_applicable_free.cpp
libs/asio/test/properties/cpp11/can_prefer_not_preferable_free_require.cpp
libs/asio/test/properties/cpp11/can_query_not_applicable_member.cpp
libs/asio/test/properties/cpp11/can_prefer_not_applicable_static.cpp
libs/asio/test/properties/cpp11/can_prefer_free_prefer.cpp
libs/asio/test/properties/cpp11/prefer_free_require.cpp
libs/asio/test/properties/cpp11/can_query_static.cpp
libs/asio/test/properties/cpp11/can_prefer_member_prefer.cpp
libs/asio/test/properties/cpp11/require_concept_static.cpp
libs/asio/test/properties/cpp11/can_query_unsupported.cpp
libs/asio/test/properties/cpp11/can_require_concept_not_applicable_unsupported.cpp
libs/asio/test/properties/cpp11/can_require_concept_static.cpp
libs/asio/test/properties/cpp11/can_require_concept_not_applicable_free.cpp
libs/asio/test/properties/cpp11/can_require_not_applicable_static.cpp
libs/asio/test/properties/cpp11/can_prefer_not_applicable_unsupported.cpp
libs/asio/test/properties/cpp11/query_member.cpp
libs/asio/test/properties/cpp11/can_require_free.cpp
libs/asio/test/properties/cpp11/can_prefer_not_applicable_free_prefer.cpp
libs/asio/test/properties/cpp11/can_require_member.cpp
libs/asio/test/properties/cpp11/can_prefer_not_applicable_free_require.cpp
libs/asio/test/properties/cpp11/require_static.cpp
libs/asio/test/properties/cpp11/can_require_concept_not_applicable_member.cpp
libs/asio/test/properties/cpp11/can_query_not_applicable_unsupported.cpp
libs/asio/test/properties/cpp11/require_member.cpp
libs/asio/test/properties/cpp11/can_prefer_not_preferable_unsupported.cpp
libs/asio/test/properties/cpp11/prefer_static.cpp
libs/asio/test/properties/cpp11/can_require_concept_unsupported.cpp
libs/asio/test/properties/cpp11/prefer_member_require.cpp
libs/asio/test/properties/cpp11/can_prefer_member_require.cpp
libs/asio/test/properties/cpp11/prefer_free_prefer.cpp
libs/asio/test/properties/cpp11/can_require_concept_not_applicable_static.cpp
libs/asio/test/properties/cpp11/can_prefer_static.cpp
libs/asio/test/properties/cpp11/can_require_not_applicable_member.cpp
libs/asio/test/properties/cpp11/can_prefer_not_preferable_member_prefer.cpp
libs/asio/test/properties/cpp11/can_require_concept_free.cpp
libs/asio/test/properties/cpp11/query_free.cpp
libs/asio/test/properties/cpp11/can_require_unsupported.cpp
libs/asio/test/properties/cpp11/can_require_static.cpp
libs/asio/test/properties/cpp03/require_concept_free.cpp
libs/asio/test/properties/cpp03/can_query_not_applicable_free.cpp
libs/asio/test/properties/cpp03/can_prefer_not_preferable_member_require.cpp
libs/asio/test/properties/cpp03/require_free.cpp
libs/asio/test/properties/cpp03/can_query_not_applicable_static.cpp
libs/asio/test/properties/cpp03/prefer_unsupported.cpp
libs/asio/test/properties/cpp03/can_prefer_unsupported.cpp
libs/asio/test/properties/cpp03/query_static.cpp
libs/asio/test/properties/cpp03/can_prefer_not_preferable_static.cpp
libs/asio/test/properties/cpp03/can_prefer_not_preferable_free_prefer.cpp
libs/asio/test/properties/cpp03/can_prefer_free_require.cpp
libs/asio/test/properties/cpp03/can_require_not_applicable_unsupported.cpp
libs/asio/test/properties/cpp03/prefer_member_prefer.cpp
libs/asio/test/properties/cpp03/require_concept_member.cpp
libs/asio/test/properties/cpp03/can_require_concept_member.cpp
libs/asio/test/properties/cpp03/can_prefer_not_applicable_member_require.cpp
libs/asio/test/properties/cpp03/can_query_member.cpp
libs/asio/test/properties/cpp03/can_prefer_not_applicable_member_prefer.cpp
libs/asio/test/properties/cpp03/can_query_free.cpp
libs/asio/test/properties/cpp03/can_require_not_applicable_free.cpp
libs/asio/test/properties/cpp03/can_prefer_not_preferable_free_require.cpp
libs/asio/test/properties/cpp03/can_query_not_applicable_member.cpp
libs/asio/test/properties/cpp03/can_prefer_not_applicable_static.cpp
libs/asio/test/properties/cpp03/can_prefer_free_prefer.cpp
libs/asio/test/properties/cpp03/prefer_free_require.cpp
libs/asio/test/properties/cpp03/can_query_static.cpp
libs/asio/test/properties/cpp03/can_prefer_member_prefer.cpp
libs/asio/test/properties/cpp03/require_concept_static.cpp
libs/asio/test/properties/cpp03/can_query_unsupported.cpp
libs/asio/test/properties/cpp03/can_require_concept_not_applicable_unsupported.cpp
libs/asio/test/properties/cpp03/can_require_concept_static.cpp
libs/asio/test/properties/cpp03/can_require_concept_not_applicable_free.cpp
libs/asio/test/properties/cpp03/can_require_not_applicable_static.cpp
libs/asio/test/properties/cpp03/can_prefer_not_applicable_unsupported.cpp
libs/asio/test/properties/cpp03/query_member.cpp
libs/asio/test/properties/cpp03/can_require_free.cpp
libs/asio/test/properties/cpp03/can_prefer_not_applicable_free_prefer.cpp
libs/asio/test/properties/cpp03/can_require_member.cpp
libs/asio/test/properties/cpp03/can_prefer_not_applicable_free_require.cpp
libs/asio/test/properties/cpp03/require_static.cpp
libs/asio/test/properties/cpp03/can_require_concept_not_applicable_member.cpp
libs/asio/test/properties/cpp03/can_query_not_applicable_unsupported.cpp
libs/asio/test/properties/cpp03/require_member.cpp
libs/asio/test/properties/cpp03/can_prefer_not_preferable_unsupported.cpp
libs/asio/test/properties/cpp03/prefer_static.cpp
libs/asio/test/properties/cpp03/can_require_concept_unsupported.cpp
libs/asio/test/properties/cpp03/prefer_member_require.cpp
libs/asio/test/properties/cpp03/can_prefer_member_require.cpp
libs/asio/test/properties/cpp03/prefer_free_prefer.cpp
libs/asio/test/properties/cpp03/can_require_concept_not_applicable_static.cpp
libs/asio/test/properties/cpp03/can_prefer_static.cpp
libs/asio/test/properties/cpp03/can_require_not_applicable_member.cpp
libs/asio/test/properties/cpp03/can_prefer_not_preferable_member_prefer.cpp
libs/asio/test/properties/cpp03/can_require_concept_free.cpp
libs/asio/test/properties/cpp03/query_free.cpp
libs/asio/test/properties/cpp03/can_require_unsupported.cpp
libs/asio/test/properties/cpp03/can_require_static.cpp
libs/asio/test/properties/cpp14/require_concept_free.cpp
libs/asio/test/properties/cpp14/can_query_not_applicable_free.cpp
libs/asio/test/properties/cpp14/can_prefer_not_preferable_member_require.cpp
libs/asio/test/properties/cpp14/require_free.cpp
libs/asio/test/properties/cpp14/can_query_not_applicable_static.cpp
libs/asio/test/properties/cpp14/prefer_unsupported.cpp
libs/asio/test/properties/cpp14/can_prefer_unsupported.cpp
libs/asio/test/properties/cpp14/query_static.cpp
libs/asio/test/properties/cpp14/can_prefer_not_preferable_static.cpp
libs/asio/test/properties/cpp14/can_prefer_not_preferable_free_prefer.cpp
libs/asio/test/properties/cpp14/can_prefer_free_require.cpp
libs/asio/test/properties/cpp14/can_require_not_applicable_unsupported.cpp
libs/asio/test/properties/cpp14/prefer_member_prefer.cpp
libs/asio/test/properties/cpp14/require_concept_member.cpp
libs/asio/test/properties/cpp14/can_require_concept_member.cpp
libs/asio/test/properties/cpp14/can_prefer_not_applicable_member_require.cpp
libs/asio/test/properties/cpp14/can_query_member.cpp
libs/asio/test/properties/cpp14/can_prefer_not_applicable_member_prefer.cpp
libs/asio/test/properties/cpp14/can_query_free.cpp
libs/asio/test/properties/cpp14/can_require_not_applicable_free.cpp
libs/asio/test/properties/cpp14/can_prefer_not_preferable_free_require.cpp
libs/asio/test/properties/cpp14/can_query_not_applicable_member.cpp
libs/asio/test/properties/cpp14/can_prefer_not_applicable_static.cpp
libs/asio/test/properties/cpp14/can_prefer_free_prefer.cpp
libs/asio/test/properties/cpp14/prefer_free_require.cpp
libs/asio/test/properties/cpp14/can_query_static.cpp
libs/asio/test/properties/cpp14/can_prefer_member_prefer.cpp
libs/asio/test/properties/cpp14/require_concept_static.cpp
libs/asio/test/properties/cpp14/can_query_unsupported.cpp
libs/asio/test/properties/cpp14/can_require_concept_not_applicable_unsupported.cpp
libs/asio/test/properties/cpp14/can_require_concept_static.cpp
libs/asio/test/properties/cpp14/can_require_concept_not_applicable_free.cpp
libs/asio/test/properties/cpp14/can_require_not_applicable_static.cpp
libs/asio/test/properties/cpp14/can_prefer_not_applicable_unsupported.cpp
libs/asio/test/properties/cpp14/query_member.cpp
libs/asio/test/properties/cpp14/can_require_free.cpp
libs/asio/test/properties/cpp14/can_prefer_not_applicable_free_prefer.cpp
libs/asio/test/properties/cpp14/can_require_member.cpp
libs/asio/test/properties/cpp14/can_prefer_not_applicable_free_require.cpp
libs/asio/test/properties/cpp14/require_static.cpp
libs/asio/test/properties/cpp14/can_require_concept_not_applicable_member.cpp
libs/asio/test/properties/cpp14/can_query_not_applicable_unsupported.cpp
libs/asio/test/properties/cpp14/require_member.cpp
libs/asio/test/properties/cpp14/can_prefer_not_preferable_unsupported.cpp
libs/asio/test/properties/cpp14/prefer_static.cpp
libs/asio/test/properties/cpp14/can_require_concept_unsupported.cpp
libs/asio/test/properties/cpp14/prefer_member_require.cpp
libs/asio/test/properties/cpp14/can_prefer_member_require.cpp
libs/asio/test/properties/cpp14/prefer_free_prefer.cpp
libs/asio/test/properties/cpp14/can_require_concept_not_applicable_static.cpp
libs/asio/test/properties/cpp14/can_prefer_static.cpp
libs/asio/test/properties/cpp14/can_require_not_applicable_member.cpp
libs/asio/test/properties/cpp14/can_prefer_not_preferable_member_prefer.cpp
libs/asio/test/properties/cpp14/can_require_concept_free.cpp
libs/asio/test/properties/cpp14/query_free.cpp
libs/asio/test/properties/cpp14/can_require_unsupported.cpp
libs/asio/test/properties/cpp14/can_require_static.cpp
libs/asio/test/socket_base.cpp
libs/asio/test/buffered_read_stream.cpp
libs/asio/test/strand.cpp
libs/asio/test/unit_test.hpp
libs/asio/test/archetypes/async_ops.hpp
libs/asio/test/archetypes/async_result.hpp
libs/asio/test/deadline_timer.cpp
libs/asio/test/compose.cpp
libs/asio/test/signal_set.cpp
libs/asio/test/system_timer.cpp
libs/asio/test/system_executor.cpp
libs/asio/test/buffers_iterator.cpp
libs/asio/test/coroutine.cpp
libs/asio/test/write.cpp
libs/asio/test/local/stream_protocol.cpp
libs/asio/test/local/connect_pair.cpp
libs/asio/test/local/datagram_protocol.cpp
libs/asio/test/latency/udp_client.cpp
libs/asio/test/latency/tcp_server.cpp
libs/asio/test/latency/udp_server.cpp
libs/asio/test/latency/tcp_client.cpp
libs/asio/test/execution/scheduler.cpp
libs/asio/test/execution/blocking_adaptation.cpp
libs/asio/test/execution/set_done.cpp
libs/asio/test/execution/outstanding_work.cpp
libs/asio/test/execution/set_error.cpp
libs/asio/test/execution/sender.cpp
libs/asio/test/execution/connect.cpp
libs/asio/test/execution/context_as.cpp
libs/asio/test/execution/bulk_guarantee.cpp
libs/asio/test/execution/set_value.cpp
libs/asio/test/execution/schedule.cpp
libs/asio/test/execution/executor.cpp
libs/asio/test/execution/prefer_only.cpp
libs/asio/test/execution/submit.cpp
libs/asio/test/execution/any_executor.cpp
libs/asio/test/execution/blocking.cpp
libs/asio/test/execution/relationship.cpp
libs/asio/test/execution/execute.cpp
libs/asio/test/execution/bulk_execute.cpp
libs/asio/test/execution/start.cpp
libs/asio/test/execution/mapping.cpp
libs/asio/test/execution/receiver.cpp
libs/asio/test/execution/operation_state.cpp
libs/asio/test/bind_cancellation_slot.cpp
libs/asio/test/use_future.cpp
libs/asio/test/random_access_file.cpp
libs/asio/test/buffer.cpp
libs/asio/test/serial_port_base.cpp
libs/asio/test/stream_file.cpp
libs/asio/test/is_write_buffered.cpp
libs/asio/test/buffered_write_stream.cpp
libs/asio/test/is_read_buffered.cpp
libs/asio/test/registered_buffer.cpp
libs/asio/test/read_at.cpp
libs/asio/test/write_at.cpp
libs/asio/test/posix/stream_descriptor.cpp
libs/asio/test/error.cpp
libs/asio/test/ssl/stream.cpp
libs/asio/test/io_context_strand.cpp
libs/asio/example/cpp17/coroutines_ts/echo_server_with_default.cpp
libs/asio/example/cpp17/coroutines_ts/refactored_echo_server.cpp
libs/asio/example/cpp17/coroutines_ts/chat_server.cpp
libs/asio/example/cpp17/coroutines_ts/echo_server.cpp
libs/asio/example/cpp17/coroutines_ts/range_based_for.cpp
libs/asio/example/cpp17/coroutines_ts/echo_server_with_as_tuple_default.cpp
libs/asio/example/cpp17/coroutines_ts/echo_server_with_as_single_default.cpp
libs/asio/example/cpp20/channels/throttling_proxy.cpp
libs/asio/example/cpp11/allocation/server.cpp
libs/asio/example/cpp11/timers/time_t_timer.cpp
libs/asio/example/cpp11/nonblocking/third_party_lib.cpp
libs/asio/example/cpp11/executors/fork_join.cpp
libs/asio/example/cpp11/executors/bank_account_1.cpp
libs/asio/example/cpp11/executors/bank_account_2.cpp
libs/asio/example/cpp11/executors/actor.cpp
libs/asio/example/cpp11/executors/priority_scheduler.cpp
libs/asio/example/cpp11/executors/pipeline.cpp
libs/asio/example/cpp11/invocation/prioritised_handlers.cpp
libs/asio/example/cpp11/spawn/parallel_grep.cpp
libs/asio/example/cpp11/spawn/echo_server.cpp
libs/asio/example/cpp11/socks4/sync_client.cpp
libs/asio/example/cpp11/socks4/socks4.hpp
libs/asio/example/cpp11/iostreams/http_client.cpp
libs/asio/example/cpp11/operations/composed_4.cpp
libs/asio/example/cpp11/operations/composed_1.cpp
libs/asio/example/cpp11/operations/composed_2.cpp
libs/asio/example/cpp11/operations/composed_3.cpp
libs/asio/example/cpp11/operations/composed_8.cpp
libs/asio/example/cpp11/operations/composed_5.cpp
libs/asio/example/cpp11/operations/composed_7.cpp
libs/asio/example/cpp11/operations/composed_6.cpp
libs/asio/example/cpp11/local/iostream_client.cpp
libs/asio/example/cpp11/local/connect_pair.cpp
libs/asio/example/cpp11/local/stream_server.cpp
libs/asio/example/cpp11/local/stream_client.cpp
libs/asio/example/cpp11/multicast/sender.cpp
libs/asio/example/cpp11/multicast/receiver.cpp
libs/asio/example/cpp11/handler_tracking/custom_tracking.hpp
libs/asio/example/cpp11/handler_tracking/async_tcp_echo_server.cpp
libs/asio/example/cpp11/timeouts/blocking_udp_client.cpp
libs/asio/example/cpp11/timeouts/async_tcp_client.cpp
libs/asio/example/cpp11/timeouts/blocking_tcp_client.cpp
libs/asio/example/cpp11/timeouts/server.cpp
libs/asio/example/cpp11/timeouts/blocking_token_tcp_client.cpp
libs/asio/example/cpp11/chat/chat_server.cpp
libs/asio/example/cpp11/chat/chat_client.cpp
libs/asio/example/cpp11/futures/daytime_client.cpp
libs/asio/example/cpp11/echo/blocking_udp_echo_client.cpp
libs/asio/example/cpp11/echo/async_udp_echo_server.cpp
libs/asio/example/cpp11/echo/blocking_tcp_echo_server.cpp
libs/asio/example/cpp11/echo/async_tcp_echo_server.cpp
libs/asio/example/cpp11/echo/blocking_tcp_echo_client.cpp
libs/asio/example/cpp11/echo/blocking_udp_echo_server.cpp
libs/asio/example/cpp11/files/async_file_copy.cpp
libs/asio/example/cpp11/files/blocking_file_copy.cpp
libs/asio/example/cpp11/buffers/reference_counted.cpp
libs/asio/example/cpp11/fork/process_per_connection.cpp
libs/asio/example/cpp11/fork/daemon.cpp
libs/asio/example/cpp11/http/server/reply.hpp
libs/asio/example/cpp11/http/server/server.cpp
libs/asio/example/cpp11/http/server/reply.cpp
libs/asio/example/cpp11/http/server/server.hpp
libs/asio/example/cpp11/http/server/connection.hpp
libs/asio/example/cpp11/http/server/connection.cpp
libs/asio/example/cpp11/ssl/client.cpp
libs/asio/example/cpp11/ssl/server.cpp
libs/asio/example/cpp03/allocation/server.cpp
libs/asio/example/cpp03/timers/time_t_timer.cpp
libs/asio/example/cpp03/nonblocking/third_party_lib.cpp
libs/asio/example/cpp03/services/basic_logger.hpp
libs/asio/example/cpp03/services/daytime_client.cpp
libs/asio/example/cpp03/services/logger_service.hpp
libs/asio/example/cpp03/windows/transmit_file.cpp
libs/asio/example/cpp03/tutorial/timer_dox.txt
libs/asio/example/cpp03/tutorial/timer3/timer.cpp
libs/asio/example/cpp03/tutorial/timer1/timer.cpp
libs/asio/example/cpp03/tutorial/daytime2/server.cpp
libs/asio/example/cpp03/tutorial/daytime5/server.cpp
libs/asio/example/cpp03/tutorial/timer4/timer.cpp
libs/asio/example/cpp03/tutorial/daytime7/server.cpp
libs/asio/example/cpp03/tutorial/daytime3/server.cpp
libs/asio/example/cpp03/tutorial/daytime4/client.cpp
libs/asio/example/cpp03/tutorial/daytime6/server.cpp
libs/asio/example/cpp03/tutorial/daytime1/client.cpp
libs/asio/example/cpp03/tutorial/timer2/timer.cpp
libs/asio/example/cpp03/tutorial/timer5/timer.cpp
libs/asio/example/cpp03/tutorial/daytime_dox.txt
libs/asio/example/cpp03/invocation/prioritised_handlers.cpp
libs/asio/example/cpp03/serialization/client.cpp
libs/asio/example/cpp03/serialization/server.cpp
libs/asio/example/cpp03/serialization/connection.hpp
libs/asio/example/cpp03/spawn/parallel_grep.cpp
libs/asio/example/cpp03/spawn/echo_server.cpp
libs/asio/example/cpp03/socks4/sync_client.cpp
libs/asio/example/cpp03/socks4/socks4.hpp
libs/asio/example/cpp03/porthopper/protocol.hpp
libs/asio/example/cpp03/porthopper/client.cpp
libs/asio/example/cpp03/porthopper/server.cpp
libs/asio/example/cpp03/iostreams/daytime_server.cpp
libs/asio/example/cpp03/iostreams/http_client.cpp
libs/asio/example/cpp03/iostreams/daytime_client.cpp
libs/asio/example/cpp03/local/iostream_client.cpp
libs/asio/example/cpp03/local/connect_pair.cpp
libs/asio/example/cpp03/local/stream_server.cpp
libs/asio/example/cpp03/local/stream_client.cpp
libs/asio/example/cpp03/multicast/sender.cpp
libs/asio/example/cpp03/multicast/receiver.cpp
libs/asio/example/cpp03/timeouts/blocking_udp_client.cpp
libs/asio/example/cpp03/timeouts/async_tcp_client.cpp
libs/asio/example/cpp03/timeouts/blocking_tcp_client.cpp
libs/asio/example/cpp03/timeouts/server.cpp
libs/asio/example/cpp03/timeouts/blocking_token_tcp_client.cpp
libs/asio/example/cpp03/chat/chat_server.cpp
libs/asio/example/cpp03/chat/chat_client.cpp
libs/asio/example/cpp03/chat/posix_chat_client.cpp
libs/asio/example/cpp03/echo/blocking_udp_echo_client.cpp
libs/asio/example/cpp03/echo/async_udp_echo_server.cpp
libs/asio/example/cpp03/echo/blocking_tcp_echo_server.cpp
libs/asio/example/cpp03/echo/async_tcp_echo_server.cpp
libs/asio/example/cpp03/echo/blocking_tcp_echo_client.cpp
libs/asio/example/cpp03/echo/blocking_udp_echo_server.cpp
libs/asio/example/cpp03/buffers/reference_counted.cpp
libs/asio/example/cpp03/fork/process_per_connection.cpp
libs/asio/example/cpp03/fork/daemon.cpp
libs/asio/example/cpp03/http/server2/io_context_pool.hpp
libs/asio/example/cpp03/http/server2/io_context_pool.cpp
libs/asio/example/cpp03/http/server2/reply.hpp
libs/asio/example/cpp03/http/server2/server.cpp
libs/asio/example/cpp03/http/server2/reply.cpp
libs/asio/example/cpp03/http/server2/server.hpp
libs/asio/example/cpp03/http/server2/connection.hpp
libs/asio/example/cpp03/http/server2/connection.cpp
libs/asio/example/cpp03/http/server4/request_parser.hpp
libs/asio/example/cpp03/http/server4/reply.hpp
libs/asio/example/cpp03/http/server4/server.cpp
libs/asio/example/cpp03/http/server4/reply.cpp
libs/asio/example/cpp03/http/server4/main.cpp
libs/asio/example/cpp03/http/server4/server.hpp
libs/asio/example/cpp03/http/server/reply.hpp
libs/asio/example/cpp03/http/server/server.cpp
libs/asio/example/cpp03/http/server/reply.cpp
libs/asio/example/cpp03/http/server/server.hpp
libs/asio/example/cpp03/http/server/connection.hpp
libs/asio/example/cpp03/http/server/connection.cpp
libs/asio/example/cpp03/http/client/sync_client.cpp
libs/asio/example/cpp03/http/client/async_client.cpp
libs/asio/example/cpp03/http/server3/reply.hpp
libs/asio/example/cpp03/http/server3/server.cpp
libs/asio/example/cpp03/http/server3/reply.cpp
libs/asio/example/cpp03/http/server3/server.hpp
libs/asio/example/cpp03/http/server3/connection.hpp
libs/asio/example/cpp03/http/server3/connection.cpp
libs/asio/example/cpp03/icmp/ipv4_header.hpp
libs/asio/example/cpp03/icmp/ping.cpp
libs/asio/example/cpp03/ssl/client.cpp
libs/asio/example/cpp03/ssl/server.cpp
libs/asio/example/cpp14/executors/fork_join.cpp
libs/asio/example/cpp14/executors/bank_account_1.cpp
libs/asio/example/cpp14/executors/bank_account_2.cpp
libs/asio/example/cpp14/executors/actor.cpp
libs/asio/example/cpp14/executors/priority_scheduler.cpp
libs/asio/example/cpp14/executors/async_2.cpp
libs/asio/example/cpp14/executors/async_1.cpp
libs/asio/example/cpp14/executors/pipeline.cpp
libs/asio/example/cpp14/deferred/deferred_1.cpp
libs/asio/example/cpp14/deferred/deferred_3.cpp
libs/asio/example/cpp14/deferred/deferred_7.cpp
libs/asio/example/cpp14/deferred/deferred_2.cpp
libs/asio/example/cpp14/deferred/deferred_4.cpp
libs/asio/example/cpp14/deferred/deferred_5.cpp
libs/asio/example/cpp14/deferred/deferred_6.cpp
libs/asio/example/cpp14/iostreams/http_client.cpp
libs/asio/example/cpp14/operations/composed_4.cpp
libs/asio/example/cpp14/operations/composed_1.cpp
libs/asio/example/cpp14/operations/composed_2.cpp
libs/asio/example/cpp14/operations/composed_3.cpp
libs/asio/example/cpp14/operations/composed_8.cpp
libs/asio/example/cpp14/operations/composed_5.cpp
libs/asio/example/cpp14/operations/composed_7.cpp
libs/asio/example/cpp14/operations/composed_6.cpp
libs/asio/example/cpp14/parallel_group/wait_for_one.cpp
libs/asio/example/cpp14/parallel_group/wait_for_all.cpp
libs/asio/example/cpp14/parallel_group/wait_for_one_error.cpp
libs/asio/example/cpp14/parallel_group/parallel_sort.cpp
libs/asio/example/cpp14/parallel_group/wait_for_one_success.cpp
libs/coroutine2/doc/motivation.qbk
libs/coroutine2/doc/coro.qbk
libs/outcome/doc/src/snippets/boost-only/asio_integration.cpp
libs/outcome/doc/src/snippets/boost-only/asio_integration_1_70.cpp
libs/beast/doc/qbk/08_design/3_websocket_zaphoyd.qbk
libs/beast/doc/qbk/08_design/4_faq.qbk
libs/beast/doc/qbk/03_core/_core.qbk
libs/beast/doc/qbk/01_intro/_intro.qbk
libs/beast/doc/qbk/07_concepts/DynamicBuffer.qbk
libs/beast/doc/qbk/release_notes.qbk
libs/beast/doc/html/beast/ref/boost__beast__basic_stream/connect/overload6.html
libs/beast/test/doc/core_1_refresher.cpp
libs/beast/test/doc/core_snippets.cpp
libs/beast/test/doc/websocket_common.ipp
libs/beast/test/doc/core_3_timeouts.cpp
libs/beast/test/doc/snippets.ipp
libs/beast/test/bench/wsload/wsload.cpp
libs/beast/test/beast/websocket/ssl.cpp
libs/beast/test/beast/websocket/timer.cpp
libs/beast/test/beast/core/async_base.cpp
libs/beast/test/beast/core/_detail_read.cpp
libs/beast/test/beast/_experimental/stream.cpp
libs/beast/CHANGELOG.md
libs/beast/example/advanced/server/advanced_server.cpp
libs/beast/example/advanced/server-flex/advanced_server_flex.cpp
libs/beast/example/websocket/server/async-ssl/websocket_server_async_ssl.cpp
libs/beast/example/websocket/server/chat-multi/net.hpp
libs/beast/example/websocket/server/sync-ssl/websocket_server_sync_ssl.cpp
libs/beast/example/websocket/server/stackless-ssl/websocket_server_stackless_ssl.cpp
libs/beast/example/websocket/server/coro/websocket_server_coro.cpp
libs/beast/example/websocket/server/coro-ssl/websocket_server_coro_ssl.cpp
libs/beast/example/websocket/server/stackless/websocket_server_stackless.cpp
libs/beast/example/websocket/server/fast/websocket_server_fast.cpp
libs/beast/example/websocket/server/async/websocket_server_async.cpp
libs/beast/example/websocket/server/sync/websocket_server_sync.cpp
libs/beast/example/websocket/client/async-ssl/websocket_client_async_ssl.cpp
libs/beast/example/websocket/client/sync-ssl/websocket_client_sync_ssl.cpp
libs/beast/example/websocket/client/coro/websocket_client_coro.cpp
libs/beast/example/websocket/client/coro-ssl/websocket_client_coro_ssl.cpp
libs/beast/example/websocket/client/async-ssl-system-executor/websocket_client_async_ssl_system_executor.cpp
libs/beast/example/websocket/client/async/websocket_client_async.cpp
libs/beast/example/websocket/client/sync/websocket_client_sync.cpp
libs/beast/example/doc/http_examples.hpp
libs/beast/example/common/server_certificate.hpp
libs/beast/example/common/root_certificates.hpp
libs/beast/example/echo-op/echo_op.cpp
libs/beast/example/http/server/async-ssl/http_server_async_ssl.cpp
libs/beast/example/http/server/small/http_server_small.cpp
libs/beast/example/http/server/sync-ssl/http_server_sync_ssl.cpp
libs/beast/example/http/server/flex/http_server_flex.cpp
libs/beast/example/http/server/stackless-ssl/http_server_stackless_ssl.cpp
libs/beast/example/http/server/coro/http_server_coro.cpp
libs/beast/example/http/server/coro-ssl/http_server_coro_ssl.cpp
libs/beast/example/http/server/stackless/http_server_stackless.cpp
libs/beast/example/http/server/fast/http_server_fast.cpp
libs/beast/example/http/server/async/http_server_async.cpp
libs/beast/example/http/server/sync/http_server_sync.cpp
libs/beast/example/http/client/async-ssl/http_client_async_ssl.cpp
libs/beast/example/http/client/sync-ssl/http_client_sync_ssl.cpp
libs/beast/example/http/client/crawl/http_crawl.cpp
libs/beast/example/http/client/coro/http_client_coro.cpp
libs/beast/example/http/client/coro-ssl/http_client_coro_ssl.cpp
libs/beast/example/http/client/async-ssl-system-executor/http_client_async_ssl_system_executor.cpp
libs/beast/example/http/client/async/http_client_async.cpp
libs/beast/example/http/client/sync/http_client_sync.cpp
libs/process/doc/extend.qbk
libs/process/doc/autodoc.xml
libs/process/doc/tutorial.qbk
libs/process/test/system_test2.cpp
libs/process/test/async_system_fail.cpp
libs/process/test/async_system_stackless.cpp
libs/process/test/bind_stderr.cpp
libs/process/test/on_exit3.cpp
libs/process/test/system_test1.cpp
libs/process/test/bind_stdout.cpp
libs/process/test/async_system_future.cpp
libs/process/test/limit_fd.cpp
libs/process/test/async_system_stackful_except.cpp
libs/process/test/bind_stdin.cpp
libs/process/test/on_exit2.cpp
libs/process/test/on_exit.cpp
libs/process/test/spawn.cpp
libs/process/test/async_fut.cpp
libs/process/test/async_system_stackful.cpp
libs/process/test/async.cpp
libs/process/test/async_pipe.cpp
libs/process/test/bind_stdout_stderr.cpp
libs/process/test/exit_code.cpp
libs/process/test/async_system_stackful_error.cpp
libs/process/test/wait.cpp
libs/process/test/spawn_fail.cpp
libs/process/example/io.cpp
libs/process/example/async_io.cpp
libs/process/example/wait.cpp
libs/thread/test/test_9303.cpp
boost/log/sinks/syslog_backend.hpp
boost/asio/basic_streambuf.hpp
boost/asio/read_until.hpp
boost/asio/executor_work_guard.hpp
boost/asio/any_io_executor.hpp
boost/asio/system_executor.hpp
boost/asio/basic_seq_packet_socket.hpp
boost/asio/error.hpp
boost/asio/basic_readable_pipe.hpp
boost/asio/executor.hpp
boost/asio/read_at.hpp
boost/asio/this_coro.hpp
boost/asio/experimental/coro.hpp
boost/asio/experimental/deferred.hpp
boost/asio/experimental/promise.hpp
boost/asio/experimental/impl/coro.hpp
boost/asio/experimental/impl/parallel_group.hpp
boost/asio/experimental/impl/use_coro.hpp
boost/asio/experimental/basic_concurrent_channel.hpp
boost/asio/experimental/parallel_group.hpp
boost/asio/experimental/basic_channel.hpp
boost/asio/experimental/use_coro.hpp
boost/asio/experimental/channel_error.hpp
boost/asio/experimental/detail/channel_operation.hpp
boost/asio/experimental/detail/completion_handler_erasure.hpp
boost/asio/experimental/detail/channel_receive_op.hpp
boost/asio/experimental/detail/impl/channel_service.hpp
boost/asio/experimental/detail/channel_service.hpp
boost/asio/experimental/detail/partial_promise.hpp
boost/asio/experimental/detail/channel_send_op.hpp
boost/asio/basic_writable_pipe.hpp
boost/asio/windows/basic_random_access_handle.hpp
boost/asio/windows/basic_stream_handle.hpp
boost/asio/windows/basic_object_handle.hpp
boost/asio/windows/basic_overlapped_handle.hpp
boost/asio/cancellation_state.hpp
boost/asio/generic/datagram_protocol.hpp
boost/asio/generic/basic_endpoint.hpp
boost/asio/generic/raw_protocol.hpp
boost/asio/generic/seq_packet_protocol.hpp
boost/asio/generic/stream_protocol.hpp
boost/asio/generic/detail/impl/endpoint.ipp
boost/asio/generic/detail/endpoint.hpp
boost/asio/completion_condition.hpp
boost/asio/handler_invoke_hook.hpp
boost/asio/thread_pool.hpp
boost/asio/ip/network_v4.hpp
boost/asio/ip/address.hpp
boost/asio/ip/basic_endpoint.hpp
boost/asio/ip/icmp.hpp
boost/asio/ip/basic_resolver_iterator.hpp
boost/asio/ip/basic_resolver_entry.hpp
boost/asio/ip/v6_only.hpp
boost/asio/ip/basic_resolver_results.hpp
boost/asio/ip/address_v4.hpp
boost/asio/ip/impl/address_v6.ipp
boost/asio/ip/impl/host_name.ipp
boost/asio/ip/impl/network_v4.hpp
boost/asio/ip/impl/address.hpp
boost/asio/ip/impl/basic_endpoint.hpp
boost/asio/ip/impl/address.ipp
boost/asio/ip/impl/network_v6.ipp
boost/asio/ip/impl/network_v4.ipp
boost/asio/ip/impl/address_v4.hpp
boost/asio/ip/impl/address_v6.hpp
boost/asio/ip/impl/address_v4.ipp
boost/asio/ip/impl/network_v6.hpp
boost/asio/ip/address_v6.hpp
boost/asio/ip/multicast.hpp
boost/asio/ip/unicast.hpp
boost/asio/ip/basic_resolver_query.hpp
boost/asio/ip/tcp.hpp
boost/asio/ip/udp.hpp
boost/asio/ip/basic_resolver.hpp
boost/asio/ip/network_v6.hpp
boost/asio/ip/detail/socket_option.hpp
boost/asio/ip/detail/impl/endpoint.ipp
boost/asio/ip/detail/endpoint.hpp
boost/asio/coroutine.hpp
boost/asio/basic_stream_file.hpp
boost/asio/basic_datagram_socket.hpp
boost/asio/basic_socket_acceptor.hpp
boost/asio/prefer.hpp
boost/asio/basic_socket_iostream.hpp
boost/asio/detached.hpp
boost/asio/uses_executor.hpp
boost/asio/buffer_registration.hpp
boost/asio/cancellation_signal.hpp
boost/asio/async_result.hpp
boost/asio/execution_context.hpp
boost/asio/impl/read_until.hpp
boost/asio/impl/read_at.hpp
boost/asio/impl/serial_port_base.ipp
boost/asio/impl/awaitable.hpp
boost/asio/impl/connect_pipe.ipp
boost/asio/impl/detached.hpp
boost/asio/impl/io_context.ipp
boost/asio/impl/write_at.hpp
boost/asio/impl/buffered_write_stream.hpp
boost/asio/impl/dispatch.hpp
boost/asio/impl/read.hpp
boost/asio/impl/compose.hpp
boost/asio/impl/thread_pool.ipp
boost/asio/impl/post.hpp
boost/asio/impl/defer.hpp
boost/asio/impl/buffered_read_stream.hpp
boost/asio/impl/execution_context.ipp
boost/asio/impl/use_future.hpp
boost/asio/impl/write.hpp
boost/asio/impl/system_context.ipp
boost/asio/impl/co_spawn.hpp
boost/asio/impl/spawn.hpp
boost/asio/impl/connect.hpp
boost/asio/impl/io_context.hpp
boost/asio/impl/connect_pipe.hpp
boost/asio/basic_file.hpp
boost/asio/basic_serial_port.hpp
boost/asio/is_executor.hpp
boost/asio/require.hpp
boost/asio/basic_stream_socket.hpp
boost/asio/write_at.hpp
boost/asio/io_context_strand.hpp
boost/asio/require_concept.hpp
boost/asio/read.hpp
boost/asio/compose.hpp
boost/asio/strand.hpp
boost/asio/local/datagram_protocol.hpp
boost/asio/local/basic_endpoint.hpp
boost/asio/local/connect_pair.hpp
boost/asio/local/stream_protocol.hpp
boost/asio/local/detail/impl/endpoint.ipp
boost/asio/local/detail/endpoint.hpp
boost/asio/buffer.hpp
boost/asio/execution/bulk_execute.hpp
boost/asio/execution/blocking.hpp
boost/asio/execution/executor.hpp
boost/asio/execution/context_as.hpp
boost/asio/execution/receiver.hpp
boost/asio/execution/prefer_only.hpp
boost/asio/execution/schedule.hpp
boost/asio/execution/outstanding_work.hpp
boost/asio/execution/set_error.hpp
boost/asio/execution/submit.hpp
boost/asio/execution/bulk_guarantee.hpp
boost/asio/execution/operation_state.hpp
boost/asio/execution/set_value.hpp
boost/asio/execution/blocking_adaptation.hpp
boost/asio/execution/sender.hpp
boost/asio/execution/mapping.hpp
boost/asio/execution/scheduler.hpp
boost/asio/execution/execute.hpp
boost/asio/execution/any_executor.hpp
boost/asio/execution/start.hpp
boost/asio/execution/set_done.hpp
boost/asio/execution/connect.hpp
boost/asio/execution/relationship.hpp
boost/asio/execution/detail/void_receiver.hpp
boost/asio/execution/detail/submit_receiver.hpp
boost/asio/execution/detail/as_invocable.hpp
boost/asio/execution/detail/as_receiver.hpp
boost/asio/execution/detail/as_operation.hpp
boost/asio/basic_deadline_timer.hpp
boost/asio/buffered_read_stream.hpp
boost/asio/placeholders.hpp
boost/asio/use_future.hpp
boost/asio/write.hpp
boost/asio/use_awaitable.hpp
boost/asio/co_spawn.hpp
boost/asio/basic_socket.hpp
boost/asio/basic_io_object.hpp
boost/asio/basic_waitable_timer.hpp
boost/asio/spawn.hpp
boost/asio/connect.hpp
boost/asio/posix/descriptor_base.hpp
boost/asio/posix/basic_descriptor.hpp
boost/asio/posix/basic_stream_descriptor.hpp
boost/asio/buffers_iterator.hpp
boost/asio/socket_base.hpp
boost/asio/io_context.hpp
boost/asio/basic_random_access_file.hpp
boost/asio/basic_raw_socket.hpp
boost/asio/basic_signal_set.hpp
boost/asio/ssl/stream.hpp
boost/asio/ssl/error.hpp
boost/asio/ssl/host_name_verification.hpp
boost/asio/ssl/stream_base.hpp
boost/asio/ssl/impl/error.ipp
boost/asio/ssl/impl/context.ipp
boost/asio/ssl/impl/context.hpp
boost/asio/ssl/rfc2818_verification.hpp
boost/asio/ssl/context_base.hpp
boost/asio/ssl/context.hpp
boost/asio/ssl/detail/io.hpp
boost/asio/ssl/detail/impl/engine.ipp
boost/asio/ssl/detail/impl/openssl_init.ipp
boost/asio/ssl/detail/shutdown_op.hpp
boost/asio/ssl/detail/write_op.hpp
boost/asio/ssl/detail/stream_core.hpp
boost/asio/ssl/detail/buffered_handshake_op.hpp
boost/asio/ssl/detail/engine.hpp
boost/asio/ssl/detail/read_op.hpp
boost/asio/ssl/detail/openssl_init.hpp
boost/asio/query.hpp
boost/asio/detail/win_iocp_null_buffers_op.hpp
boost/asio/detail/winrt_socket_connect_op.hpp
boost/asio/detail/winrt_timer_scheduler.hpp
boost/asio/detail/reactive_socket_sendto_op.hpp
boost/asio/detail/win_iocp_file_service.hpp
boost/asio/detail/win_iocp_serial_port_service.hpp
boost/asio/detail/io_uring_descriptor_read_at_op.hpp
boost/asio/detail/win_iocp_socket_connect_op.hpp
boost/asio/detail/io_uring_socket_recvfrom_op.hpp
boost/asio/detail/consuming_buffers.hpp
boost/asio/detail/reactor_op_queue.hpp
boost/asio/detail/win_iocp_socket_recv_op.hpp
boost/asio/detail/winapp_thread.hpp
boost/asio/detail/deadline_timer_service.hpp
boost/asio/detail/null_static_mutex.hpp
boost/asio/detail/win_iocp_socket_recvfrom_op.hpp
boost/asio/detail/dev_poll_reactor.hpp
boost/asio/detail/descriptor_read_op.hpp
boost/asio/detail/io_object_impl.hpp
boost/asio/detail/winrt_socket_send_op.hpp
boost/asio/detail/reactive_null_buffers_op.hpp
boost/asio/detail/win_iocp_handle_service.hpp
boost/asio/detail/std_static_mutex.hpp
boost/asio/detail/winrt_async_manager.hpp
boost/asio/detail/memory.hpp
boost/asio/detail/win_iocp_socket_service.hpp
boost/asio/detail/null_thread.hpp
boost/asio/detail/win_mutex.hpp
boost/asio/detail/handler_cont_helpers.hpp
boost/asio/detail/service_registry.hpp
boost/asio/detail/io_uring_socket_accept_op.hpp
boost/asio/detail/null_mutex.hpp
boost/asio/detail/win_iocp_handle_read_op.hpp
boost/asio/detail/io_uring_socket_service.hpp
boost/asio/detail/conditionally_enabled_mutex.hpp
boost/asio/detail/socket_option.hpp
boost/asio/detail/win_iocp_overlapped_ptr.hpp
boost/asio/detail/posix_mutex.hpp
boost/asio/detail/io_uring_socket_sendto_op.hpp
boost/asio/detail/resolver_service.hpp
boost/asio/detail/resolve_endpoint_op.hpp
boost/asio/detail/reactive_socket_recvmsg_op.hpp
boost/asio/detail/impl/win_iocp_io_context.ipp
boost/asio/detail/impl/winrt_timer_scheduler.hpp
boost/asio/detail/impl/pipe_select_interrupter.ipp
boost/asio/detail/impl/win_iocp_socket_service_base.ipp
boost/asio/detail/impl/handler_tracking.ipp
boost/asio/detail/impl/io_uring_file_service.ipp
boost/asio/detail/impl/strand_executor_service.ipp
boost/asio/detail/impl/winsock_init.ipp
boost/asio/detail/impl/strand_service.ipp
boost/asio/detail/impl/win_mutex.ipp
boost/asio/detail/impl/posix_tss_ptr.ipp
boost/asio/detail/impl/dev_poll_reactor.hpp
boost/asio/detail/impl/eventfd_select_interrupter.ipp
boost/asio/detail/impl/io_uring_service.ipp
boost/asio/detail/impl/posix_serial_port_service.ipp
boost/asio/detail/impl/buffer_sequence_adapter.ipp
boost/asio/detail/impl/kqueue_reactor.ipp
boost/asio/detail/impl/strand_executor_service.hpp
boost/asio/detail/impl/service_registry.ipp
boost/asio/detail/impl/dev_poll_reactor.ipp
boost/asio/detail/impl/signal_set_service.ipp
boost/asio/detail/impl/winrt_timer_scheduler.ipp
boost/asio/detail/impl/win_tss_ptr.ipp
boost/asio/detail/impl/select_reactor.ipp
boost/asio/detail/impl/scheduler.ipp
boost/asio/detail/impl/posix_thread.ipp
boost/asio/detail/impl/descriptor_ops.ipp
boost/asio/detail/impl/win_event.ipp
boost/asio/detail/impl/win_iocp_file_service.ipp
boost/asio/detail/impl/resolver_service_base.ipp
boost/asio/detail/impl/socket_ops.ipp
boost/asio/detail/impl/win_iocp_io_context.hpp
boost/asio/detail/impl/epoll_reactor.ipp
boost/asio/detail/impl/posix_event.ipp
boost/asio/detail/impl/throw_error.ipp
boost/asio/detail/impl/socket_select_interrupter.ipp
boost/asio/detail/impl/reactive_descriptor_service.ipp
boost/asio/detail/impl/win_static_mutex.ipp
boost/asio/detail/impl/select_reactor.hpp
boost/asio/detail/impl/win_iocp_serial_port_service.ipp
boost/asio/detail/impl/win_object_handle_service.ipp
boost/asio/detail/impl/io_uring_socket_service_base.ipp
boost/asio/detail/impl/posix_mutex.ipp
boost/asio/detail/impl/win_thread.ipp
boost/asio/detail/impl/io_uring_descriptor_service.ipp
boost/asio/detail/impl/win_iocp_handle_service.ipp
boost/asio/detail/impl/strand_service.hpp
boost/asio/detail/impl/winrt_ssocket_service_base.ipp
boost/asio/detail/impl/reactive_socket_service_base.ipp
boost/asio/detail/io_uring_socket_send_op.hpp
boost/asio/detail/wait_handler.hpp
boost/asio/detail/buffer_sequence_adapter.hpp
boost/asio/detail/io_uring_descriptor_write_at_op.hpp
boost/asio/detail/win_iocp_socket_recvmsg_op.hpp
boost/asio/detail/io_uring_socket_service_base.hpp
boost/asio/detail/descriptor_ops.hpp
boost/asio/detail/signal_handler.hpp
boost/asio/detail/base_from_cancellation_state.hpp
boost/asio/detail/win_object_handle_service.hpp
boost/asio/detail/descriptor_write_op.hpp
boost/asio/detail/reactive_socket_connect_op.hpp
boost/asio/detail/reactive_descriptor_service.hpp
boost/asio/detail/win_iocp_overlapped_op.hpp
boost/asio/detail/string_view.hpp
boost/asio/detail/epoll_reactor.hpp
boost/asio/detail/io_uring_socket_recv_op.hpp
boost/asio/detail/conditionally_enabled_event.hpp
boost/asio/detail/win_static_mutex.hpp
boost/asio/detail/winrt_resolver_service.hpp
boost/asio/detail/winrt_ssocket_service.hpp
boost/asio/detail/handler_tracking.hpp
boost/asio/detail/reactive_socket_service_base.hpp
boost/asio/detail/io_uring_wait_op.hpp
boost/asio/detail/win_iocp_socket_send_op.hpp
boost/asio/detail/io_uring_null_buffers_op.hpp
boost/asio/detail/io_uring_socket_recvmsg_op.hpp
boost/asio/detail/timer_queue.hpp
boost/asio/detail/io_uring_service.hpp
boost/asio/detail/null_socket_service.hpp
boost/asio/detail/kqueue_reactor.hpp
boost/asio/detail/resolver_service_base.hpp
boost/asio/detail/std_mutex.hpp
boost/asio/detail/reactive_socket_recvfrom_op.hpp
boost/asio/detail/win_iocp_io_context.hpp
boost/asio/detail/winrt_resolve_op.hpp
boost/asio/detail/buffered_stream_storage.hpp
boost/asio/detail/io_uring_descriptor_write_op.hpp
boost/asio/detail/scheduler.hpp
boost/asio/detail/reactive_wait_op.hpp
boost/asio/detail/resolve_query_op.hpp
boost/asio/detail/blocking_executor_op.hpp
boost/asio/detail/reactive_socket_service.hpp
boost/asio/detail/io_uring_descriptor_read_op.hpp
boost/asio/detail/win_iocp_wait_op.hpp
boost/asio/detail/io_uring_socket_connect_op.hpp
boost/asio/detail/io_uring_descriptor_service.hpp
boost/asio/detail/signal_set_service.hpp
boost/asio/detail/null_reactor.hpp
boost/asio/detail/completion_handler.hpp
boost/asio/detail/select_reactor.hpp
boost/asio/detail/winrt_ssocket_service_base.hpp
boost/asio/detail/handler_alloc_helpers.hpp
boost/asio/detail/reactive_socket_recv_op.hpp
boost/asio/detail/winrt_utils.hpp
boost/asio/detail/reactive_socket_send_op.hpp
boost/asio/detail/win_iocp_socket_accept_op.hpp
boost/asio/detail/wince_thread.hpp
boost/asio/detail/win_iocp_handle_write_op.hpp
boost/asio/detail/work_dispatcher.hpp
boost/asio/detail/handler_work.hpp
boost/asio/detail/handler_type_requirements.hpp
boost/asio/detail/handler_invoke_helpers.hpp
boost/asio/detail/posix_static_mutex.hpp
boost/asio/detail/strand_service.hpp
boost/asio/detail/is_buffer_sequence.hpp
boost/asio/detail/winsock_init.hpp
boost/asio/detail/thread_group.hpp
boost/asio/detail/noncopyable.hpp
boost/asio/detail/win_iocp_socket_service_base.hpp
boost/asio/detail/reactive_socket_accept_op.hpp
boost/asio/detail/winrt_socket_recv_op.hpp
boost/asio/basic_socket_streambuf.hpp
boost/beast/websocket/impl/ssl.hpp
boost/beast/core/impl/basic_stream.hpp
boost/beast/core/impl/async_base.hpp
boost/beast/core/detect_ssl.hpp
boost/beast/core/basic_stream.hpp
boost/beast/core/async_base.hpp
boost/beast/core/detail/bind_handler.hpp
boost/beast/core/detail/is_invocable.hpp
boost/beast/core/detail/config.hpp
boost/beast/core/detail/bind_default_executor.hpp
boost/beast/_experimental/test/stream.hpp
boost/process/io.hpp
boost/process/async.hpp
boost/process/system.hpp
boost/process/async_pipe.hpp
boost/process/async_system.hpp
boost/process/spawn.hpp
boost/process/detail/windows/on_exit.hpp
boost/process/detail/windows/io_context_ref.hpp
boost/process/detail/windows/async_in.hpp
boost/process/detail/windows/async_pipe.hpp
boost/process/detail/windows/async_out.hpp
boost/process/detail/async_handler.hpp
boost/process/detail/traits/async.hpp
boost/process/detail/posix/on_exit.hpp
boost/process/detail/posix/io_context_ref.hpp
boost/process/detail/posix/async_in.hpp
boost/process/detail/posix/async_pipe.hpp
boost/process/detail/posix/async_out.hpp
boost/process/detail/posix/sigchld_service.hpp
tools/docca/include/docca/base-config.xsl</details>




**8. Скомпилирутйе *boost*. Можно воспользоваться [инструкцией](https://www.boost.org/doc/libs/1_61_0/more/getting_started/unix-variants.html#or-build-custom-binaries) или [ссылкой](https://codeyarns.com/2017/01/24/how-to-build-boost-on-linux/).**
```bash
$ ./boost_1_78_0/bootstrap.sh
$ ./boost-1_78_0/b2
```

<details> <summary>Performing configuration checks </summary>

    - default address-model    : 64-bit (cached) [1]
    - default architecture     : x86 (cached) [1]

Building the Boost C++ Libraries.


    - compiler supports SSE2   : yes (cached) [2]
    - compiler supports SSE4.1 : yes (cached) [2]
    - has std::atomic_ref      : no  (cached) [2]
    - has statx                : yes (cached) [2]
    - has init_priority attribute : yes (cached) [2]
    - has stat::st_blksize     : yes (cached) [2]
    - has stat::st_mtim        : yes (cached) [2]
    - has stat::st_mtimensec   : no  (cached) [2]
    - has stat::st_mtimespec   : no  (cached) [2]
    - has stat::st_birthtim    : no  (cached) [2]
    - has stat::st_birthtimensec : no  (cached) [2]
    - has stat::st_birthtimespec : no  (cached) [2]
    - cxx11_auto_declarations  : yes (cached) [2]
    - cxx11_constexpr          : yes (cached) [2]
    - cxx11_defaulted_functions : yes (cached) [2]
    - cxx11_final              : yes (cached) [2]
    - cxx11_hdr_mutex          : yes (cached) [2]
    - cxx11_hdr_tuple          : yes (cached) [2]
    - cxx11_lambdas            : yes (cached) [2]
    - cxx11_noexcept           : yes (cached) [2]
    - cxx11_nullptr            : yes (cached) [2]
    - cxx11_rvalue_references  : yes (cached) [2]
    - cxx11_template_aliases   : yes (cached) [2]
    - cxx11_thread_local       : yes (cached) [2]
    - cxx11_variadic_templates : yes (cached) [2]
    - cxx11_auto_declarations  : yes (cached) [3]
    - cxx11_constexpr          : yes (cached) [3]
    - cxx11_defaulted_functions : yes (cached) [3]
    - cxx11_final              : yes (cached) [3]
    - cxx11_hdr_mutex          : yes (cached) [3]
    - cxx11_hdr_tuple          : yes (cached) [3]
    - cxx11_lambdas            : yes (cached) [3]
    - cxx11_noexcept           : yes (cached) [3]
    - cxx11_nullptr            : yes (cached) [3]
    - cxx11_rvalue_references  : yes (cached) [3]
    - cxx11_template_aliases   : yes (cached) [3]
    - cxx11_thread_local       : yes (cached) [3]
    - cxx11_variadic_templates : yes (cached) [3]
    - has_icu builds           : yes (cached) [2]
warning: Graph library does not contain MPI-based parallel components.
note: to enable them, add "using mpi ;" to your user-config.jam.
note: to suppress this message, pass "--without-graph_parallel" to bjam.
    - zlib                     : yes (cached)
    - bzip2                    : yes (cached)
    - lzma                     : yes (cached)
    - zstd                     : yes (cached)
    - has_lzma_cputhreads builds : yes (cached) [2]
    - cxx11_decltype           : yes (cached) [2]
    - cxx11_basic_alignas      : yes (cached) [2]
    - iconv (libc)             : yes (cached) [2]
    - icu                      : yes (cached) [2]
    - lockfree boost::atomic_flag : yes (cached) [2]
    - native atomic int32 supported : yes (cached) [2]
    - native syslog supported  : yes (cached) [2]
    - pthread supports robust mutexes : yes (cached) [2]
    - compiler supports SSSE3  : yes (cached) [2]
    - compiler supports AVX2   : yes (cached) [2]
    - gcc visibility           : yes (cached) [2]
    - sfinae_expr              : yes (cached) [2]
    - cxx11_unified_initialization_syntax : yes (cached) [2]
    - cxx11_hdr_initializer_list : yes (cached) [2]
    - cxx11_hdr_chrono         : yes (cached) [2]
    - cxx11_numeric_limits     : yes (cached) [2]
    - cxx11_hdr_array          : yes (cached) [2]
    - cxx11_hdr_atomic         : yes (cached) [2]
    - cxx11_hdr_type_traits    : yes (cached) [2]
    - cxx11_allocator          : yes (cached) [2]
    - cxx11_explicit_conversion_operators : yes (cached) [2]
    - long double support      : yes (cached) [2]
warning: skipping optional Message Passing Interface (MPI) library.
note: to enable MPI support, add "using mpi ;" to user-config.jam.
note: to suppress this message, pass "--without-mpi" to bjam.
note: otherwise, you can safely ignore this message.
    - cxx11_static_assert      : yes (cached) [2]
    - std::fstream is moveable and swappable : yes (cached) [2]
    - Has Large File Support   : yes (cached) [2]
    - Has attribute init_priority : yes (cached) [2]
    - libbacktrace builds      : no  (cached) [2]
    - libbacktrace builds      : no  (cached) [3]
    - addr2line builds         : yes (cached) [2]
    - WinDbg builds            : no  (cached) [2]
    - WinDbg builds            : no  (cached) [3]
    - WinDbgCached builds      : no  (cached) [2]
    - WinDbgCached builds      : no  (cached) [3]
    - BOOST_COMP_GNUC >= 4.3.0 : yes (cached) [2]
    - BOOST_COMP_GNUC >= 4.3.0 : yes (cached) [4]
    - compiler supports SSE2   : yes (cached) [4]
    - compiler supports SSE4.1 : yes (cached) [4]
    - has std::atomic_ref      : no  (cached) [4]
    - has statx                : yes (cached) [4]
    - has init_priority attribute : yes (cached) [4]
    - has stat::st_blksize     : yes (cached) [4]
    - has stat::st_mtim        : yes (cached) [4]
    - has stat::st_mtimensec   : no  (cached) [4]
    - has stat::st_mtimespec   : no  (cached) [4]
    - has stat::st_birthtim    : no  (cached) [4]
    - has stat::st_birthtimensec : no  (cached) [4]
    - has stat::st_birthtimespec : no  (cached) [4]
    - cxx11_auto_declarations  : yes (cached) [4]
    - cxx11_constexpr          : yes (cached) [4]
    - cxx11_defaulted_functions : yes (cached) [4]
    - cxx11_final              : yes (cached) [4]
    - cxx11_hdr_mutex          : yes (cached) [4]
    - cxx11_hdr_tuple          : yes (cached) [4]
    - cxx11_lambdas            : yes (cached) [4]
    - cxx11_noexcept           : yes (cached) [4]
    - cxx11_nullptr            : yes (cached) [4]
    - cxx11_rvalue_references  : yes (cached) [4]
    - cxx11_template_aliases   : yes (cached) [4]
    - cxx11_thread_local       : yes (cached) [4]
    - cxx11_variadic_templates : yes (cached) [4]
    - cxx11_auto_declarations  : yes (cached) [5]
    - cxx11_constexpr          : yes (cached) [5]
    - cxx11_defaulted_functions : yes (cached) [5]
    - cxx11_final              : yes (cached) [5]
    - cxx11_hdr_mutex          : yes (cached) [5]
    - cxx11_hdr_tuple          : yes (cached) [5]
    - cxx11_lambdas            : yes (cached) [5]
    - cxx11_noexcept           : yes (cached) [5]
    - cxx11_nullptr            : yes (cached) [5]
    - cxx11_rvalue_references  : yes (cached) [5]
    - cxx11_template_aliases   : yes (cached) [5]
    - cxx11_thread_local       : yes (cached) [5]
    - cxx11_variadic_templates : yes (cached) [5]
    - has_icu builds           : yes (cached) [4]
    - zlib                     : yes (cached) [6]
    - bzip2                    : yes (cached) [6]
    - lzma                     : yes (cached) [6]
    - zstd                     : yes (cached) [6]
    - has_lzma_cputhreads builds : yes (cached) [4]
    - cxx11_decltype           : yes (cached) [4]
    - cxx11_basic_alignas      : yes (cached) [4]
    - iconv (libc)             : yes (cached) [4]
    - icu                      : yes (cached) [4]
    - lockfree boost::atomic_flag : yes (cached) [4]
    - native atomic int32 supported : yes (cached) [4]
    - native syslog supported  : yes (cached) [4]
    - pthread supports robust mutexes : yes (cached) [4]
    - compiler supports SSSE3  : yes (cached) [4]
    - compiler supports AVX2   : yes (cached) [4]
    - gcc visibility           : yes (cached) [4]
    - sfinae_expr              : yes (cached) [4]
    - cxx11_unified_initialization_syntax : yes (cached) [4]
    - cxx11_hdr_initializer_list : yes (cached) [4]
    - cxx11_hdr_chrono         : yes (cached) [4]
    - cxx11_numeric_limits     : yes (cached) [4]
    - cxx11_hdr_array          : yes (cached) [4]
    - cxx11_hdr_atomic         : yes (cached) [4]
    - cxx11_hdr_type_traits    : yes (cached) [4]
    - cxx11_allocator          : yes (cached) [4]
    - cxx11_explicit_conversion_operators : yes (cached) [4]
    - long double support      : yes (cached) [4]
    - cxx11_static_assert      : yes (cached) [4]
    - std::fstream is moveable and swappable : yes (cached) [4]
    - Has Large File Support   : yes (cached) [4]
    - Has attribute init_priority : yes (cached) [4]
    - libbacktrace builds      : no  (cached) [4]
    - libbacktrace builds      : no  (cached) [5]
    - addr2line builds         : yes (cached) [4]
    - WinDbg builds            : no  (cached) [4]
    - WinDbg builds            : no  (cached) [5]
    - WinDbgCached builds      : no  (cached) [4]
    - WinDbgCached builds      : no  (cached) [5]

[1] gcc-11
[2] gcc-11/release/python-3.10/threadapi-pthread/threading-multi/visibility-hidden
[3] gcc-11/release/build-no/python-3.10/threadapi-pthread/threading-multi/visibility-hidden
[4] gcc-11/release/link-static/python-3.10/threadapi-pthread/threading-multi/visibility-hidden
[5] gcc-11/release/build-no/link-static/python-3.10/threadapi-pthread/threading-multi/visibility-hidden
[6] link-static

Component configuration:

    - atomic                   : building
    - chrono                   : building
    - container                : building
    - context                  : building
    - contract                 : building
    - coroutine                : building
    - date_time                : building
    - exception                : building
    - fiber                    : building
    - filesystem               : building
    - graph                    : building
    - graph_parallel           : building
    - headers                  : building
    - iostreams                : building
    - json                     : building
    - locale                   : building
    - log                      : building
    - math                     : building
    - mpi                      : building
    - nowide                   : building
    - program_options          : building
    - python                   : building
    - random                   : building
    - regex                    : building
    - serialization            : building
    - stacktrace               : building
    - system                   : building
    - test                     : building
    - thread                   : building
    - timer                    : building
    - type_erasure             : building
    - wave                     : building

...patience...
...patience...
...patience...
...patience...
...patience...
...patience...
...patience...
...found 17313 targets...
...updating 86 targets...
boost-install.generate-cmake-config- bin.v2/libs/fiber/build/stage/boost_fiber-config.cmake
boost-install.generate-cmake-config- bin.v2/libs/filesystem/build/stage/boost_filesystem-config.cmake
boost-install.generate-cmake-config- bin.v2/libs/graph/build/stage/boost_graph-config.cmake
boost-install.generate-cmake-config- bin.v2/libs/regex/build/stage/boost_regex-config.cmake
boost-install.generate-cmake-config- bin.v2/libs/graph_parallel/build/stage/boost_graph_parallel-config.cmake
boost-install.generate-cmake-config- bin.v2/libs/iostreams/build/stage/boost_iostreams-config.cmake
boost-install.generate-cmake-config- bin.v2/libs/json/build/stage/boost_json-config.cmake
boost-install.generate-cmake-config- bin.v2/libs/locale/build/stage/boost_locale-config.cmake
boost-install.generate-cmake-config- bin.v2/libs/system/build/stage/boost_system-config.cmake
boost-install.generate-cmake-config- bin.v2/libs/thread/build/stage/boost_thread-config.cmake
boost-install.generate-cmake-config- bin.v2/libs/log/build/stage/boost_log-config.cmake
boost-install.generate-cmake-config- bin.v2/libs/log/build/stage/boost_log_setup-config.cmake
boost-install.generate-cmake-config- bin.v2/libs/math/build/stage/boost_math_c99-config.cmake
boost-install.generate-cmake-config- bin.v2/libs/math/build/stage/boost_math_c99f-config.cmake
boost-install.generate-cmake-config- bin.v2/libs/math/build/stage/boost_math_c99l-config.cmake
boost-install.generate-cmake-config- bin.v2/libs/math/build/stage/boost_math_tr1-config.cmake
common.copy /home/augustus/TIMP/lab1/boost_1_78_0/stage/lib/cmake/boost_graph_parallel-1.78.0/boost_graph_parallel-config.cmake
common.copy /home/augustus/TIMP/lab1/boost_1_78_0/stage/lib/cmake/boost_iostreams-1.78.0/boost_iostreams-config.cmake
common.copy /home/augustus/TIMP/lab1/boost_1_78_0/stage/lib/cmake/boost_json-1.78.0/boost_json-config.cmake
common.copy /home/augustus/TIMP/lab1/boost_1_78_0/stage/lib/cmake/boost_locale-1.78.0/boost_locale-config.cmake
common.copy /home/augustus/TIMP/lab1/boost_1_78_0/stage/lib/cmake/boost_system-1.78.0/boost_system-config.cmake
common.copy /home/augustus/TIMP/lab1/boost_1_78_0/stage/lib/cmake/boost_thread-1.78.0/boost_thread-config.cmake
common.copy /home/augustus/TIMP/lab1/boost_1_78_0/stage/lib/cmake/boost_filesystem-1.78.0/boost_filesystem-config.cmake
common.copy /home/augustus/TIMP/lab1/boost_1_78_0/stage/lib/cmake/boost_graph-1.78.0/boost_graph-config.cmake
common.copy /home/augustus/TIMP/lab1/boost_1_78_0/stage/lib/cmake/boost_regex-1.78.0/boost_regex-config.cmake
common.copy /home/augustus/TIMP/lab1/boost_1_78_0/stage/lib/cmake/boost_math_c99f-1.78.0/boost_math_c99f-config.cmake
boost-install.generate-cmake-config- bin.v2/libs/math/build/stage/boost_math_tr1f-config.cmake
boost-install.generate-cmake-config- bin.v2/libs/math/build/stage/boost_math_tr1l-config.cmake
boost-install.generate-cmake-config- bin.v2/libs/mpi/build/stage/boost_mpi-config.cmake
boost-install.generate-cmake-config- bin.v2/libs/nowide/build/stage/boost_nowide-config.cmake
boost-install.generate-cmake-config- bin.v2/libs/program_options/build/stage/boost_program_options-config.cmake
common.copy /home/augustus/TIMP/lab1/boost_1_78_0/stage/lib/cmake/boost_log-1.78.0/boost_log-config.cmake
common.copy /home/augustus/TIMP/lab1/boost_1_78_0/stage/lib/cmake/boost_math_c99l-1.78.0/boost_math_c99l-config.cmake
common.copy /home/augustus/TIMP/lab1/boost_1_78_0/stage/lib/cmake/boost_log_setup-1.78.0/boost_log_setup-config.cmake
common.copy /home/augustus/TIMP/lab1/boost_1_78_0/stage/lib/cmake/boost_math_c99-1.78.0/boost_math_c99-config.cmake
common.copy /home/augustus/TIMP/lab1/boost_1_78_0/stage/lib/cmake/boost_fiber-1.78.0/boost_fiber-config.cmake
common.copy /home/augustus/TIMP/lab1/boost_1_78_0/stage/lib/cmake/boost_math_tr1-1.78.0/boost_math_tr1-config.cmake
boost-install.generate-cmake-config- bin.v2/libs/python/build/stage/boost_python-config.cmake
boost-install.generate-cmake-config- bin.v2/libs/random/build/stage/boost_random-config.cmake
boost-install.generate-cmake-config- bin.v2/libs/serialization/build/stage/boost_serialization-config.cmake
boost-install.generate-cmake-config- bin.v2/libs/serialization/build/stage/boost_wserialization-config.cmake
boost-install.generate-cmake-config- bin.v2/libs/stacktrace/build/stage/boost_stacktrace_noop-config.cmake
boost-install.generate-cmake-config- bin.v2/libs/stacktrace/build/stage/boost_stacktrace_addr2line-config.cmake
boost-install.generate-cmake-config- bin.v2/libs/stacktrace/build/stage/boost_stacktrace_basic-config.cmake
boost-install.generate-cmake-config- bin.v2/libs/test/build/stage/boost_prg_exec_monitor-config.cmake
boost-install.generate-cmake-config- bin.v2/libs/test/build/stage/boost_test_exec_monitor-config.cmake
boost-install.generate-cmake-config- bin.v2/libs/test/build/stage/boost_unit_test_framework-config.cmake
boost-install.generate-cmake-config- bin.v2/libs/timer/build/stage/boost_timer-config.cmake
common.copy /home/augustus/TIMP/lab1/boost_1_78_0/stage/lib/cmake/boost_math_tr1f-1.78.0/boost_math_tr1f-config.cmake
common.copy /home/augustus/TIMP/lab1/boost_1_78_0/stage/lib/cmake/boost_nowide-1.78.0/boost_nowide-config.cmake
common.copy /home/augustus/TIMP/lab1/boost_1_78_0/stage/lib/cmake/boost_program_options-1.78.0/boost_program_options-config.cmake
common.copy /home/augustus/TIMP/lab1/boost_1_78_0/stage/lib/cmake/boost_math_tr1l-1.78.0/boost_math_tr1l-config.cmake
common.copy /home/augustus/TIMP/lab1/boost_1_78_0/stage/lib/cmake/boost_wserialization-1.78.0/boost_wserialization-config.cmake
common.copy /home/augustus/TIMP/lab1/boost_1_78_0/stage/lib/cmake/boost_mpi-1.78.0/boost_mpi-config.cmake
common.copy /home/augustus/TIMP/lab1/boost_1_78_0/stage/lib/cmake/boost_stacktrace_basic-1.78.0/boost_stacktrace_basic-config.cmake
common.copy /home/augustus/TIMP/lab1/boost_1_78_0/stage/lib/cmake/boost_serialization-1.78.0/boost_serialization-config.cmake
common.copy /home/augustus/TIMP/lab1/boost_1_78_0/stage/lib/cmake/boost_stacktrace_addr2line-1.78.0/boost_stacktrace_addr2line-config.cmake
common.copy /home/augustus/TIMP/lab1/boost_1_78_0/stage/lib/cmake/boost_random-1.78.0/boost_random-config.cmake
common.copy /home/augustus/TIMP/lab1/boost_1_78_0/stage/lib/cmake/boost_python-1.78.0/boost_python-config.cmake
common.copy /home/augustus/TIMP/lab1/boost_1_78_0/stage/lib/cmake/boost_prg_exec_monitor-1.78.0/boost_prg_exec_monitor-config.cmake
common.copy /home/augustus/TIMP/lab1/boost_1_78_0/stage/lib/cmake/boost_test_exec_monitor-1.78.0/boost_test_exec_monitor-config.cmake
common.copy /home/augustus/TIMP/lab1/boost_1_78_0/stage/lib/cmake/boost_unit_test_framework-1.78.0/boost_unit_test_framework-config.cmake
common.copy /home/augustus/TIMP/lab1/boost_1_78_0/stage/lib/cmake/boost_stacktrace_noop-1.78.0/boost_stacktrace_noop-config.cmake
boost-install.generate-cmake-config- bin.v2/libs/type_erasure/build/stage/boost_type_erasure-config.cmake
boost-install.generate-cmake-config- bin.v2/libs/wave/build/stage/boost_wave-config.cmake
boost-install.generate-cmake-config- bin.v2/libs/headers/build/stage/boost_headers-config.cmake
boost-install.generate-cmake-config- bin.v2/libs/atomic/build/stage/boost_atomic-config.cmake
boost-install.generate-cmake-config- bin.v2/libs/chrono/build/stage/boost_chrono-config.cmake
common.copy /home/augustus/TIMP/lab1/boost_1_78_0/stage/lib/cmake/boost_timer-1.78.0/boost_timer-config.cmake
boost-install.generate-cmake-config- bin.v2/libs/container/build/stage/boost_container-config.cmake
boost-install.generate-cmake-config- bin.v2/libs/contract/build/stage/boost_contract-config.cmake
boost-install.generate-cmake-config- bin.v2/libs/context/build/stage/boost_context-config.cmake
boost-install.generate-cmake-config- bin.v2/libs/date_time/build/stage/boost_date_time-config.cmake
boost-install.generate-cmake-config- bin.v2/libs/coroutine/build/stage/boost_coroutine-config.cmake
boost-install.generate-cmake-config- bin.v2/libs/exception/build/stage/boost_exception-config.cmake
common.copy /home/augustus/TIMP/lab1/boost_1_78_0/stage/lib/cmake/boost_wave-1.78.0/boost_wave-config.cmake
common.copy /home/augustus/TIMP/lab1/boost_1_78_0/stage/lib/cmake/boost_headers-1.78.0/boost_headers-config.cmake
common.copy /home/augustus/TIMP/lab1/boost_1_78_0/stage/lib/cmake/boost_type_erasure-1.78.0/boost_type_erasure-config.cmake
common.copy /home/augustus/TIMP/lab1/boost_1_78_0/stage/lib/cmake/boost_chrono-1.78.0/boost_chrono-config.cmake
common.copy /home/augustus/TIMP/lab1/boost_1_78_0/stage/lib/cmake/boost_contract-1.78.0/boost_contract-config.cmake
common.copy /home/augustus/TIMP/lab1/boost_1_78_0/stage/lib/cmake/boost_atomic-1.78.0/boost_atomic-config.cmake
common.copy /home/augustus/TIMP/lab1/boost_1_78_0/stage/lib/cmake/boost_date_time-1.78.0/boost_date_time-config.cmake
common.copy /home/augustus/TIMP/lab1/boost_1_78_0/stage/lib/cmake/boost_container-1.78.0/boost_container-config.cmake
common.copy /home/augustus/TIMP/lab1/boost_1_78_0/stage/lib/cmake/boost_exception-1.78.0/boost_exception-config.cmake
common.copy /home/augustus/TIMP/lab1/boost_1_78_0/stage/lib/cmake/boost_coroutine-1.78.0/boost_coroutine-config.cmake
common.copy /home/augustus/TIMP/lab1/boost_1_78_0/stage/lib/cmake/boost_context-1.78.0/boost_context-config.cmake
...updated 86 targets...


The Boost C++ Libraries were successfully built!

The following directory should be added to compiler include paths:

    /home/augustus/TIMP/lab1/boost_1_78_0

The following directory should be added to linker library paths:

    /home/augustus/TIMP/lab1/boost_1_78_0/stage/lib
 
</details>



**9. Перенесите все скомпилированные на предыдущем шаге статические библиотеки в директорию `~/boost-libs`.**
```bash
$ cp -r boost_1_78_0/libs ~/boost-libs
```
**10. Подсчитайте сколько занимает дискового пространства каждый файл в этой директории.**
```bash
$ ls -l -R -S -h
```

**11. Найдите *топ10* самых "тяжёлых".**
```bash
$ ls -l -R -S | head -10

>> -rw-r--r--   1 user users 5,6M мар  3 14:03 ls_out
-rwxr-xr-x   1 user users 254K мар  2 08:53 b2
-rw-r--r--   1 user users 115K мар  3 14:02 output
-rw-r--r--   1 user users  20K мар  6 15:02 comp_output
-rw-r--r--   1 user users  20K дек  2 09:45 boostcpp.jam
drwxr-xr-x 135 user users  12K дек  2 10:18 boost
-rw-r--r--   1 user users  12K дек  2 09:45 Jamroot
-rwxr-xr-x   1 user users  11K дек  2 09:45 bootstrap.sh

```





















