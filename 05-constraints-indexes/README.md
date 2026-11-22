## Ограничения и индексы
-   ```addPrimaryKey``` (создание первичного ключа для таблицы) - `tableName`, `columnNames`, `constraintName`; обеспечивает уникальность и не-null строк
-   ```addForeignKeyConstraint``` (создание связи между таблицами по внешнему ключу) - `baseTableName`, `baseColumnNames`, `referencedTableName`, `referencedColumnNames`, `onDelete="CASCADE"`
-   ```addUniqueConstraint``` (гарантия уникальности значений в одной или нескольких колонках) - предотвращает дублирование бизнес-ключей (например `email`, `inn`)
-   ```createIndex``` (создание индекса для ускорения выборок и JOIN операций) - `indexName`, `tableName`, `columns`; поддержка `unique="true"`
-   ```dropIndex``` (удаление устаревшего или неэффективного индекса) - освобождает дисковое пространство и ускоряет операции INSERT/UPDATE
-   ```dropForeignKeyConstraint``` (удаление внешнего ключа при рефакторинге связей) - разрывает жёсткую зависимость между таблицами
-   ```addCheckConstraint``` (добавление правила валидации значений на уровне СУБД) - условие проверки, например `age >= 18` или `price > 0`
