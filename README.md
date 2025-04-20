# DevLink Backend

> see also: [DevLink Frontend](https://github.com/DevLink-dev/devlink-frontend-svelte)!

Backend for the DevLink platform - developed with Java Spring

## Description

The DevLink Backend allows developers to link up and share project ideas to work on as a community.

This project provides a REST API that allows users to create and manage their own profiles.
They can also create, manage and join projects to work on as a community.
This allows developers to link up all around the world and learn new skills that will help them master coding and get the job they want.

This project is developed using the [Java Spring Framework](https://spring.io).
It allows the use of [well-established tools](https://spring.io/projects) included in it.
This reduces the amount of work required to implement new features.
Using a widespread high-level language like Java also assures that the project is easy to maintain and update.
Tools like [Lombok](https://projectlombok.org/) are used to reduce boilerplate code.

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
   
To use this project, it is advised to use the corresponding [Frontend](https://github.com/DevLink-dev/devlink-frontend-svelte). 

## Development

This project is developed following the conventions listed below.

### Conventions

The following are lists of conventions that either *should* be followed or *must* be followed when contributing to this project. 