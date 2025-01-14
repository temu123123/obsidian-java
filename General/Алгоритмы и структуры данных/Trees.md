#### Деревья (Trees)

- **Описание**: Дерево — это иерархическая структура данных, состоящая из узлов, каждый из которых содержит элемент данных и ссылки на дочерние узлы. Виды деревьев включают бинарные деревья, деревья поиска и сбалансированные деревья.
    
    - **Бинарные деревья (Binary Trees)**: Каждый узел имеет не более двух потомков (левого и правого).
    - **Бинарные деревья поиска (Binary Search Trees, BST)**: Левый потомок содержит значения, меньшие, чем у родителя, правый потомок — значения, большие, чем у родителя.
    - **AVL деревья**: Сбалансированные бинарные деревья поиска, где разница высоты левого и правого поддерева любого узла не превышает 1.
- **Основные операции**: Вставка, удаление, поиск элементов.
    
- **Преимущества**: Эффективные операции поиска, вставки и удаления (O(log n) для сбалансированных деревьев).
    
- **Недостатки**: Необходимость поддержания сбалансированности, дополнительные затраты на перестроение дерева.