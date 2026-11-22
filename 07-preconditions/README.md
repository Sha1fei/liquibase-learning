## Условия выполнения (Preconditions)
-   ```preConditions``` (проверка состояния базы данных перед применением изменений) - защищает от повторного создания таблиц или сбоев при несовпадении версий
-   ```tableExists / tableIsEmpty``` (проверка наличия или пустоты таблицы) - `tableName="orders"`; предотвращает попытку повторного создания таблицы
-   ```columnExists``` (проверка существования колонки перед её модификацией) - `tableName="users"`, `columnName="status"`
-   ```sqlCheck``` (проверка состояния через выполнение пользовательского SQL запроса) - `expectedResult="0"`, `SELECT COUNT(*) FROM users WHERE email IS NULL`
-   ```onFail="MARK_RAN / HALT / CONTINUE / WARN"``` (реакция Liquibase при невыполнении условия preCondition) - `MARK_RAN` — пометить как выполненный без запуска; `HALT` — прервать миграцию
-   ```onError="HALT / CONTINUE / WARN"``` (реакция на непредвиденную ошибку при проверке условий) - определяет поведение при сбое запроса preCondition
-   ```dbms type="postgresql"``` (выполнение changeSet только на указанном типе СУБД) - адаптация миграций под особенности H2 в тестах и PostgreSQL в проде
