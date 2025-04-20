# DevLink Backend

Backend for the DevLink platform - developed with Java Spring

## Technology Overview

- [Java Spring](https://spring.io/) for dependency injection
  - [Spring Boot](https://spring.io/projects/spring-boot) as REST web server
  - [Spring Data JPA](https://spring.io/projects/spring-data-jpa) as ORM
- [PostgreSQL](https://www.postgresql.org/) as DBMS
- [Lombok](https://projectlombok.org/) for boilerplate code reduction
- Unit testing:
  - [JUnit](https://junit.org/junit5/) as testing framework
  - [AssertJ](https://assertj.github.io/doc/) for assertions
  - [mockito](https://site.mockito.org/) for mocking
  - [Instancio](https://www.instancio.org/) for test data generation

## Installation and Usage

1. Have [Docker](https://www.docker.com/) set up and running
2. Clone the repository, e.g. with:
    ```sh
    git clone https://github.com/DevLink-dev/devlink-backend-java.git
    cd devlink-backend-java
    ```
3. Make a **copy** of [`.env.example`](.env.example) and rename it to `.env` (will be git-ignored)
4. Add your environment secrets to [`.env`](.env) (will be used by both the database and the Spring application)
5. Start Docker containers for database and Spring application:
    ```sh
    docker compose up -d
    ```