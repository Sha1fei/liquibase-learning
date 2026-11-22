## Интеграция со Spring Boot
-   ```spring-boot-starter-liquibase``` (стартер для автоматического запуска миграций при старте Spring приложения) - добавляет Liquibase в жизненный цикл контекста приложения
-   ```spring.liquibase.change-log``` (указание пути к главному файлу changelog) - стандартное значение: `classpath:db/changelog/db.changelog-master.yaml`
-   ```spring.liquibase.enabled=false``` (отключение автоматического запуска миграций) - полезно при локальной разработке, интеграционном тестировании или ручном запуске через CI/CD
-   ```spring.liquibase.contexts``` (передача активных контекстов Liquibase из конфигурации Spring) - связка с профилями приложения: `spring.liquibase.contexts=${spring.profiles.active}`
-   ```spring.liquibase.drop-first=true``` (полная очистка схемы БД перед выполнением миграций) - удобно для dev-среды и in-memory БД (H2) для старта с чистого листа
-   ```spring.liquibase.default-schema``` (задание схемы по умолчанию для накатывания таблиц) - разграничение многосхемных баз данных (multi-tenant / multi-schema)
-   ```spring.liquibase.clear-checksums``` (автоматическая очистка контрольных сумм при старте) - решение проблемы изменившихся скриптов на этапе активной разработки
-   ```интеграция с JPA (Hibernate ddl-auto=validate)``` (совместная работа Liquibase и Hibernate) - Liquibase отвечает за изменение схемы, а Hibernate только проверяет её соответствие сущностям
