- **Класс String** Основной класс для создания и управления строками в Java, представляющий собой массив символов до Java 9 и массив байт начиная с Java 9.
- **Интернирование строк** Механизм оптимизации памяти, позволяющий хранить только уникальные значения строковых литералов в специальном пуле строк.
- **Создание и хранение строк** Объекты String можно создавать с помощью строковых литералов или конструктора, при этом строки, созданные как литералы, хранятся в пуле строк, а созданные через конструктор — в куче
- **Дедупликация** Процесс, при котором JVM переприсваивает адреса поля `value` нескольких объектов String с одинаковым текстом, чтобы они ссылались на один и тот же участок памяти. Это позволяет экономить память и уменьшать нагрузку на сборщик мусора.