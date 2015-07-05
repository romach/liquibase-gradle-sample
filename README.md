# Приклад роботи з liquibase і gradle

## Вимоги

* Gradle;
* PostgreSQL;

## Пояснення
### changelog.xml
Файл `changelog.xml` (взято з http://www.liquibase.org/) містить список змін,
які вносились в базу даних.

1. Створення таблиці `person(id, firstname, lastname, state)`;

2. Додавання стовбця `username` до таблиці `person`;

3. Створення таблиці `state`;

### build.gradle
Містить дві задачі:

* `update` - оновлення БД до актуального стану

* `rollbackCount 1` - відкат стану БД на одну зміну

### liquibase.properties
Містить налаштування БД - **треба встановити відповідно до власних налаштувань 
БД**.

## Запуск

* cтворити базу даних `test`

* `gradle update` - оновлення БД відповідно до `changelog.xml`

* `gradle rollback` - відкат на один changeset