
# Задача

Разработать многоканальный повторитель цифровых символов.

## Требования

1. Программа принимает цифровые символы и управляющие команды на TCP-сокетах с
   портами 9000-9009. Каждый повторитель соответствует одному порту.

2. Алгоритм повторителя описывается конечным автоматом с состояниями STOP,
   ECHO, PAUSE, GENERATE, LATCH. Входными сигналами автомата являются буквы
   's', 'p', 'e', 'l', цифры 0-9, а также истечение таймаута.

3. В состоянии ECHO повторитель воспроизводит каждую цифру, прочитанную из
   сокета, в состоянии GENERATE повторитель периодически воспроизводит цифру,
   полученную в состоянии LATCH.

4. Многоканальность (одновременная обработка событий для нескольких
   повторителей) обеспечивается системным вызовом **select()**.

# Упрощенная задача

Исключить из конечного автомата состояния GENERATE и PAUSE.
