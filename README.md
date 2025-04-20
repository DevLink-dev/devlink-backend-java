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

#### Java

- URLs must be `kebab-case`
- Packages:
  - Names must be `snake_case`
- Classes:
  - Names must be `PascalCase`
  - Annotations should have the following order:
    - Spring:
      - Bean type (`@Component`, `@Configuration`, `@RestController`, `@Service`, ...)
      - JPA:
        - `@Entity`
        - Constraints (`@UniqueConstraint`, ...)
    - Lombok:
      - constructors:
        - `@AllArgsConstructor`
        - `@NoArgsConstructor`
        - `@RequiredArgsConstructor`
      - `@Getter`
      - `@Setter`
      - `@EqualsAndHashCode`
      - ...
  - Should be structured as follows:
    - `static` constants and variables
    - Instance attributes
    - Constructors
    - `static` functions
    - Instance methods
- `static` Constants:
  - Names must be `SCREAMING_SNAKE_CASE`
- Instance Attributes and Method Parameters:
  - Names must be `camelCase`
  - Should be `final` unless there is a reason to change
- Methods:
  - Names must be `camelCase`
  - Should be at most around **15** lines long
  - Should reference down to other `private` methods unless there is a specific reason not to (top-down structure)
  - Indentations should not be more than 3 levels deep (counting method indentation level in class as zero)
    ```java
    public class Foo {
        // This is level 0.
        public void bar() {
            // This is level 1.
            for (int i = 0; i < 10; i++) {
                // This is level 2.
                for (int j = 0; j < 10; j++) {
                    // This is level 3.
                    if ((i + j) % 2 == 0) {
                        // This is level 4 (forbidden).
                        break;
                    }
                }
            }
        }
    }
    ```
- Javadoc:
  - Must be added to: 
    - `public` methods and functions of classes, excluding getters, setters and constructors
  - Should be added to:
    - all `private` members of which the purpose is not obvious or the logic is difficult to comprehend
  - May be added to:
    - `public static` constants
    - other `private` members