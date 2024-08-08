# Spring Boot

My Spring Boot notes

> [!NOTE]
> This notes is incomplete (and may contain inaccuracies) and is only based on what I've learned about the framework so far.


## Setup

```bash
# Install SDKMAN!
curl -s "https://get.sdkman.io" | bash

# Setup SDKMAN!
source "$HOME/.sdkman/bin/sdkman-init.sh"

# Install Java and Maven
sdk install java
sdk install maven
```


## Packages

- Lombok — library to reduce boilerplate code
- JPA (Java Persistence API) — API for persistence and ORM


## `application.properties`

- `spring.application.name` - name of the spring app
- `server.port` - specifies the port to use
- `spring.datasource.url` - JDBC database URL
    - `jdbc:<db_type>://<host>/<db_name>`
    - `db_type`: `mysql` | `postgresql`
    - `host`: `localhost` | `172.X.X.X`
- `spring.datasource.username` - Database username
- `spring.datasource.password` - Database user password
- `spring.jpa.properties.hibernate.dialect` -
- `spring.jpa.hibernate.ddl-auto` - DDL (Data Definition Language)
    - `none` - turns off DDL generation
    - `validate` - validates if tables and columns exists, otherwise throws and error
    - `update` - development; automatically modify schema to add new additions on restart
    - `create` - drops existing tables then creates new tables
    - `create-drop` - similar to `create` but drops all DB after operations are completed
- `spring.datasource.driver-class-name` - classname of the JDBC driver to communicate with DB
- `spring.jpa.properties.hibernate.dialect` - specifies the dialect to use for the database
    - `org.hibernate.dialect.MySQLDialect`
    - `org.hibernate.dialect.PostgreSQLDialect`
- `spring.jpa.properties.hibernate.jdbc.time_zone` - specifies the timezone


## Maven

```bash
# Remove the existing build (target/) directory
mvn clean

# Install dependencies
mvn install

# Run project
mvn spring-boot:run
```
