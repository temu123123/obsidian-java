
**CQRS** (Command Query Responsibility Segregation) — это паттерн, разделяющий операции чтения и записи данных на разные модели.

#### Основные функции:

- **Команды (Commands):** Обработчики операций записи данных.
- **Запросы (Queries):** Обработчики операций чтения данных.

#### Преимущества:

- Улучшение производительности за счет оптимизации операций чтения и записи.
- Повышение масштабируемости и гибкости системы.
- Упрощение управления сложными бизнес-логиками.