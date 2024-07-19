#### java.util.concurrent.Executor

Интерфейс [java.util.concurrent.Executor](https://docs.oracle.com/javase/8/docs/api/java/util/concurrent/Executor.html) предоставляет один метод execute, который является заменой обычного создания потока. Однако определение метода execute  несколько отличается. Низкоуровневый вариант создаёт новый поток и сразу же его запускает. В зависимости от реализации Executor-а метод execute  может делать то же самое, но обычно он использует уже существующий рабочий поток для запуска r, либо r  помещается в очередь, где дожидается освобождения рабочего потока.

Реализации executor-ов в java.util.concurrent  созданы для использования с более продвинутыми интерфейсами ExecutorService  и ScheduledExecutorService, но они также работают и с интерфейсом Executor.
#### java.util.concurrent.ExecutorService

Интерфейс [java.util.concurrent.ExecutorService](https://docs.oracle.com/javase/8/docs/api/java/util/concurrent/ExecutorService.html) расширяет интерфейс [Executor](https://docs.oracle.com/javase/8/docs/api/java/util/concurrent/Executor.html), добавляя множество новых методов. Основной метод — метод submit, который принимает как Runnable, так и интерфейс java.util.concurrent.Callable<V>  с единственным методом V call() , который позволяет заданиям возвращать значение. Метод submit  возвращает интерфейс java.util.concurrent.Future, который используется для получения результата и контролирования состояния потока.

#### java.util.concurrent.ScheduledExecutorService

Интерфейс [java.util.concurrent.ScheduledExecutorService](https://docs.oracle.com/javase/8/docs/api/java/util/concurrent/ScheduledExecutorService.html) расширяет интерфейс java.util.concurrent.ExecutorService  и добавляет методы schedule*, которые позволяют запланировать выполнение задания.