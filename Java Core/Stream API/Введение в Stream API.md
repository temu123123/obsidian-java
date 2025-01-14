Начиная с JDK 8 в Java появился новый API - Stream API. Его задача - упростить работу с наборами данных, в частности, упростить операции фильтрации, сортировки и другие манипуляции с данными. Вся основная функциональность данного API сосредоточена в пакете java.util.stream.

Ключевым понятием в Stream API является поток данных. Вообще сам термин "поток" довольно перегружен в программировании в целом и в Java в частности. В одной из предыдущих глав рассматривалась работа с символьными и байтовыми потоками при чтении-записи файлов. Применительно к Stream API поток представляет канал передачи данных из источника данных. Причем в качестве источника могут выступать как файлы, так и массивы и коллекции.

Одной из отличительных черт Stream API является применение лямбда-выражений, которые позволяют значительно сократить запись выполняемых действий.

При ближайшем рассмотрении мы можем найти в других технологиях программирования аналоги подобного API. В частности, в языке C# некоторым аналогом Stream API будет технология LINQ.
При работе со Stream API важно понимать, что все операции с потоками бывают либо терминальными (terminal), либо промежуточными (intermediate). Промежуточные операции возвращают трансформированный поток.
В основе Stream API лежит интерфейс BaseStream.
BaseStream определяет базовый функционал для работы с потоками, которые реализуется через его методы:

- void close(): закрывает поток
    
- boolean isParallel(): возвращает true, если поток является параллельным
    
- Iterator<Т> iterator(): возвращает ссылку на итератор потока
    
- Spliterator<Т> spliterator(): возвращает ссылку на сплитератор потока
    
- S parallel(): возвращает параллельный поток (параллельные потоки могут задействовать несколько ядер процессора в многоядерных архитектурах)
    
- S sequential(): возвращает последовательный поток
    
- S unordered(): возвращает неупорядоченный поток
    

От интерфейса BaseStream наследуется ряд интерфейсов, предназначенных для создания конкретных потоков:

- Stream<T>: используется для потоков данных, представляющих любой ссылочный тип
    
- IntStream: используется для потоков с типом данных int
    
- DoubleStream: используется для потоков с типом данных double
    
- LongStream: используется для потоков с типом данных long
    

При работе с потоками, которые представляют определенный примитивный тип - double, int, long проще использовать интерфейсы DoubleStream, IntStream, LongStream. Но в большинстве случаев, как правило, работа происходит с более сложными данными, для которых предназначен интерфейс `Stream<T>`. Рассмотрим некоторые его методы:

- boolean allMatch(Predicate<? super T> predicate): возвращает true, если все элементы потока удовлетворяют условию в предикате. Терминальная операция
    
- boolean anyMatch(Predicate<? super T> predicate): возвращает true, если хоть один элемент потока удовлетворяют условию в предикате. Терминальная операция
    
- <R,A> R collect(Collector<? super T,A,R> collector): добавляет элементы в неизменяемый контейнер с типом R. T представляет тип данных из вызывающего потока, а A - тип данных в контейнере. Терминальная операция
    
- long count(): возвращает количество элементов в потоке. Терминальная операция.
    
- Stream<T> concat​(Stream<? extends T> a, Stream<? extends T> b): объединяет два потока. Промежуточная операция
    
- Stream<T> distinct(): возвращает поток, в котором имеются только уникальные данные с типом T. Промежуточная операция
    
- Stream<T> dropWhile​(Predicate<? super T> predicate): пропускает элементы, которые соответствуют условию в predicate, пока не попадется элемент, который не соответствует условию. Выбранные элементы возвращаются в виде потока. Промежуточная операция.
    
- Stream<T> filter(Predicate<? super T> predicate): фильтрует элементы в соответствии с условием в предикате. Промежуточная операция
    
- Optional<T> findFirst(): возвращает первый элемент из потока. Терминальная операция
    
- Optional<T> findAny(): возвращает первый попавшийся элемент из потока. Терминальная операция
    
- void forEach(Consumer<? super T> action): для каждого элемента выполняется действие action. Терминальная операция
    
- Stream<T> limit(long maxSize): оставляет в потоке только maxSize элементов. Промежуточная операция
    
- Optional<T> max(Comparator<? super T> comparator): возвращает максимальный элемент из потока. Для сравнения элементов применяется компаратор comparator. Терминальная операция
    
- Optional<T> min(Comparator<? super T> comparator): возвращает минимальный элемент из потока. Для сравнения элементов применяется компаратор comparator. Терминальная операция
    
- <R> Stream<R> map(Function<? super T,? extends R> mapper): преобразует элементы типа T в элементы типа R и возвращает поток с элементами R. Промежуточная операция
    
- <R> Stream<R> flatMap(Function<? super T, ? extends Stream<? extends R>> mapper): позволяет преобразовать элемент типа T в несколько элементов типа R и возвращает поток с элементами R. Промежуточная операция
    
- boolean noneMatch(Predicate<? super T> predicate): возвращает true, если ни один из элементов в потоке не удовлетворяет условию в предикате. Терминальная операция
    
- Stream<T> skip(long n): возвращает поток, в котором отсутствуют первые n элементов. Промежуточная операция.
    
- Stream<T> sorted(): возвращает отсортированный поток. Промежуточная операция.
    
- Stream<T> sorted(Comparator<? super T> comparator): возвращает отсортированный в соответствии с компаратором поток. Промежуточная операция.
    
- Stream<T> takeWhile​(Predicate<? super T> predicate): выбирает из потока элементы, пока они соответствуют условию в predicate. Выбранные элементы возвращаются в виде потока. Промежуточная операция.
    
- Object[] toArray(): возвращает массив из элементов потока. Терминальная операция.
    

Несмотря на то, что все эти операции позволяют взаимодействовать с потоком как неким набором данных наподобие коллекции, важно понимать отличие коллекций от потоков:

- Потоки не хранят элементы. Элементы, используемые в потоках, могут храниться в коллекции, либо при необходимости могут быть напрямую сгенерированы.
    
- Операции с потоками не изменяют источника данных. Операции с потоками лишь возвращают новый поток с результатами этих операций.
    
- Для потоков характерно отложенное выполнение. То есть выполнение всех операций с потоком происходит лишь тогда, когда выполняется терминальная операция и возвращается конкретный результат, а не новый поток.