# Liquibase Learning

Заметки по изучению Liquibase (управление миграциями и версионированием баз данных).

## Содержание

1.  [Liquibase Core](./01-liquibase-core) (основы управления схемой БД и отслеживание истории миграций) — changelog, changeSet, DATABASECHANGELOG, DATABASECHANGELOGLOCK
2.  [Форматы Changelog](./02-changelog-formats) (выбор удобного формата описания миграций) — YAML, XML, JSON, SQL (formatted SQL)
3.  [Операции с таблицами](./03-table-changes) (создание, изменение и удаление таблиц базы данных) — createTable, dropTable, renameTable
4.  [Операции с колонками](./04-column-changes) (добавление, модификация типов данных и переименование колонок) — addColumn, dropColumn, modifyDataType, renameColumn
5.  [Ограничения и индексы](./05-constraints-indexes) (обеспечение целостности данных и производительности поиска) — addPrimaryKey, addForeignKeyConstraint, addUniqueConstraint, createIndex
6.  [Управление данными](./06-data-management) (наполнение справочников, вставка и обновление данных при миграциях) — insert, update, delete, loadData (CSV/TSV), sql
7.  [Условия выполнения (Preconditions)](./07-preconditions) (проверка состояния БД перед выполнением changeSet во избежание сбоев) — tableExists, columnExists, sqlCheck, onFail, onError
8.  [Контексты и метки (Contexts & Labels)](./08-contexts-labels) (выборочный запуск миграций под разные окружения и задачи) — context (dev/test/prod), labels, tagDatabase
9.  [Откат изменений (Rollback)](./09-rollback) (возврат схемы базы данных к предыдущему состоянию) — rollback блок, rollback tag, rollbackCount, автоматический откат
10. [Структурирование и подключение файлов](./10-include-files) (модульное разделение миграций и построение master changelog) — include, includeAll, relativeToChangelogFile
11. [Переменные и свойства (Properties)](./11-properties) (параметризация changelog под разные СУБД и окружения) — property, subst:value, dbms, placeholder
12. [Команды Liquibase CLI](./12-cli-commands) (ручное управление миграциями и диагностика состояния БД) — update, status, history, diff, clearCheckSums, releaseLocks
13. [Интеграция со Spring Boot](./13-spring-boot) (автоматическое применение миграций при старте микросервиса) — spring-boot-starter-liquibase, application.yml, auto-run, spring profiles
14. [Генерация changelog и сравнение схем](./14-diff-changelog) (реверс-инжиниринг существующей БД и синхронизация схем) — generateChangeLog, diff, diffChangeLog
15. [Лучшие практики](./15-best-practices) (паттерны безопасного версионирования БД в production и CI/CD) — zero-downtime миграции, идемпотентность, runOnChange, runAlways
