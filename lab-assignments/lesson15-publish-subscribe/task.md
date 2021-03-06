
# Базовая задача

Разработать приложение для отслеживания изменений в конфигурационной СУБД.
Регистрация подписки на уведомления и получение уведомлений об изменениях
осуществляется с помощью протокола JSON-RPC. При получении уведомления
новая версия конфигурации выводится в стандартный вывод эмулятора терминала.

## Описание базовой задачи

См. Лабораторная работа №14.

Конфигурационная СУБД и JSON-документ, содержащий конфигурацию для СУБД,
берутся из лабораторной работы №14. Исполняемые файлы с клиентом
*./lab_15_client_mips* или *./lab_15_client_x86*, который позволяет изменять
конфигурацию сетевых интерфейсов в конфигурационной СУБД,
находятся в директории с текущим заданием.

## Алгоритм решения базовой задачи

1. Принять следующее макроопределение для публичного адреса СУБД:

    ```c
    #define SOCK_DATABASE_PATH "/tmp/sock_seqpacket_cdb"
    ```

2. Отправить конфигурационной СУБД запрос на получение конфигурации
   всех сетевых интерфейсов.

3. Вывести ответ от СУБД в стандартный поток вывода эмулятора терминала.

4. Подписаться на уведомления об изменении конфигурации сетевых интерфейсов.

5. Принять уведомление об изменении конфигурации сетевого интерфейса.

6. Вывести новую конфигурацию сетевого интерфейса в стандартный поток
   вывода эмулятора терминала.

7. Вернуться к пункту №5.

[1]: https://www.jsonrpc.org/specification
[2]: https://support.smartbear.com/alertsite/docs/monitors/api/endpoint/jsonpath.html
[3]: https://jansson.readthedocs.io/en/2.12/

## Примеры для базовой задачи

См. Лабораторная работа №14.

# Усложненная задача

В дополнение к базовой задаче реализовать применение настроек сетевых
интерфейсов, по уведомлениям от конфигурационной СУБД, с помощью пакета
**iproute2**. Фактические настройки сетевых интерфейсов, полученные после
попытки применения настроек из конфигурационной СУБД, записать в виде статусных
данных в конфигурационную СУБД.

## Описание усложненной задачи

См. Лабораторная работа №14.

# Наблюдение результатов

Запуск конфигурационной СУБД осуществляется с помощью команды:

```console
$ ./lab_14_database_mips -f ./configuration.json -t
```

Запуск клиента конфигурационной СУБД осуществляется с помощью команды:

```console
$ ./lab_15_client_mips -h
```
