# <img width="64" height="64" alt="desafio" src="https://github.com/user-attachments/assets/20c01a8e-51bf-4633-abee-f9e2edaddd38" /> Desafio: Lab Publicando Sua API REST na Nuvem Usando Spring Boot 3 e Java 17 
Este repositório reúne os principais aprendizados adquiridos durante o **Bootcamp GFT - Desenvolvimento Java com IA - Curso: Banco de Dados, Padrões de Projeto e APIs com Spring Boot** da plataforma DIO.me. 
Este projeto foi desenvolvido como parte do desafio da Digital Innovation One (DIO), com o objetivo de aplicar os principais padrões de projeto na construção de uma API REST moderna utilizando **Java 17** e **Spring Boot 3**, aplicando boas práticas de arquitetura, documentação e persistência de dados.

---

## <img width="64" height="64" alt="missao" src="https://github.com/user-attachments/assets/df928293-a0a0-4b74-84c7-5af678e7f32f" /> Sobre o Desafio
O desafio proposto é uma iniciativa educacional que conecta desenvolvedores com o mercado financeiro, promovendo capacitação prática com tecnologias modernas. 
Não cheguei a fazer o deploy na nuvem, mas assim que o fizer, atualizo o repostório!

O projeto simula uma API de uma conta bancária simples com recursos como:
- Cartões do Cliente
- Notícias
- Feature
- Usuários

## <img width="64" height="64" alt="roda-dentada" src="https://github.com/user-attachments/assets/492f13ff-7dd3-45be-a84a-35886f6827c8" /> Tecnologias Utilizadas

- **Java 17**
- **Spring Boot 3**
- **Spring Data JPA**
- **H2 Database** (ambiente de desenvolvimento)
- **PostgreSQL** (ambiente de produção)
- **Springdoc OpenAPI (Swagger UI)** – documentação interativa
- **Gradle** – gerenciamento de dependências
- **IntelliJ IDEA** – ambiente de desenvolvimento
- **Railway** – deploy na nuvem (opcional)

## <img width="64" height="64" alt="project-management" src="https://github.com/user-attachments/assets/01d49d2c-9a70-4ffd-bbe5-975113762e68" /> Criação do Projeto
O projeto foi gerado via [Spring Initializr](https://start.spring.io/) com as seguintes dependências:

- Spring Web
- Spring Data JPA
- PostgreSQL Driver
- H2 Database
- Spring Boot DevTools
- Spring Boot Test

## <img width="64" height="64" alt="estrutura-hierarquica" src="https://github.com/user-attachments/assets/22fd9c46-ba9c-4008-87de-10542de975e9" /> Diagrama de Classes

```mermaid

classDiagram

    class User {

        -String name

        -Account account

        -List~Feature~ features

        -Card card

        -List~News~ news

    }



    class Account {

        -String number

        -String agency

        -double balance

        -double limit

    }


    class Feature {

        -String icon

        -String description

    }


    class Card {

        -String number

        -double limit

    }


    class News {

        -String icon

        -String description

    }


    User "1" *-- "1" Account

    User "1" *-- "1"  Card

    User "1" *-- "N"  Feature

    User "1" *-- "N"  News

```

## <img width="64" height="64" alt="gerenciamento-de-banco-de-dados" src="https://github.com/user-attachments/assets/941b0623-a468-4ab7-b76b-11b865df5832" /> Banco de Dados

Durante o desenvolvimento, foi utilizado o **H2 Database**, um banco em memória leve e de fácil visualização via console:

- Console: `http://localhost:8080/h2-console`
- JDBC URL: `jdbc:h2:mem:sdw2025`
- Usuário: `sdw2025`
- Senha: *(em branco)*

Para produção, o projeto está preparado para uso com **PostgreSQL**, com configuração via `application-prod.yml`.

## <img width="64" height="64" alt="documentacao" src="https://github.com/user-attachments/assets/a77ef82b-186b-43b0-b12d-7711a56f3d6e" /> Documentação da API

A documentação interativa da API é gerada automaticamente com **Swagger UI**:

- Acesse: `http://localhost:8080/swagger-ui/index.html`
- Endpoint da especificação: `/v3/api-docs`

## <img width="64" height="64" alt="estrutura" src="https://github.com/user-attachments/assets/758642bc-fd11-460b-8b62-a2eccf4a8ca0" /> Estrutura do Projeto

```
src/
├── main/ │
├── java/me.dio/
│ │ ├── controller/
| |     └── exception/
│ │ ├── domain/
│ │     └── model/ 
| |     └── repository/
│ │ ├── service/
│ │     └── impl/
│ └── resources/
│   ├── application.dev.yml
│   └── data.sql (opcional)
```

## <img width="64" height="64" alt="funcional" src="https://github.com/user-attachments/assets/4464d0b0-d843-435d-90bb-80b34eaadd18" /> Funcionalidades

- Cadastro de usuários com validação de número de conta
- Consulta de usuário por ID
- Tratamento global de exceções com `@RestControllerAdvice`
- Documentação automática com Swagger
- Deploy preparado para ambientes como Railway

## <img width="64" height="64" alt="laboratorio-virtual" src="https://github.com/user-attachments/assets/14b3924c-f9bd-4310-8bd9-a17a8a886de6" /> Testes
Os testes são executados com JUnit 5 e Spring Boot Starter Test:
```bash
./gradlew test
```
## <img width="64" height="64" alt="tecnologia" src="https://github.com/user-attachments/assets/05b3fb05-f593-4d1f-9cd8-ddee58ad941a" /> Deploy
O projeto pode ser facilmente publicado na nuvem com Railway, utilizando o Procfile já incluído:

```
web: java -jar build/libs/santander-dev-week-2025-0.0.1-SNAPSHOT.jar
```

## <img width="64" height="64" alt="desenvolvedor" src="https://github.com/user-attachments/assets/331b9486-e799-4106-bbfb-8579fbe7042b" /> Desenvolvedora
Izaura TM - responsável pelo projeto.

## <img width="64" height="64" alt="ajuda-do-bot" src="https://github.com/user-attachments/assets/711b1fdc-22aa-4abb-9eed-b42803ccea39" /> Contribuições
Sinta-se à vontade para abrir issues ou enviar pull requests com melhorias, sugestões ou novas funcionalidades!

> Este conteúdo faz parte do projeto **Publicando Sua API REST na Nuvem Usando Spring Boot 3, Java 17 e Railway - Laboratório** da plataforma DIO.me.

---

 ### <img width="32" height="32" alt="certo" src="https://github.com/user-attachments/assets/a1dca3a6-bcfd-47f8-a12c-5354878bce78" /> Links de Referência:
 
- [Spring Initializr](https://start.spring.io/index.html)
- [Configurações do Projeto](https://start.spring.io/#!type=gradle-project&language=java&platformVersion=3.5.6&packaging=jar&jvmVersion=17&groupId=me.dio&artifactId=santander-dev-week-2025&name=santander-dev-week-2025&description=Java%20RESTful%20API%20criada%20para%20Santander%20Dev%20Week%202025&packageName=me.dio.santander-dev-week-2025&dependencies=web,data-jpa,h2,postgresql)
- [Mermaid - Ferramenta de Diagramação e Gráficos](https://mermaid.js.org)
- [Swagger Editor](https://editor.swagger.io/)
- [IntelliJ IDEA](https://www.jetbrains.com/pt-br/idea/)
- [JSON Editor online](https://jsoneditoronline.org/#left=local.posuha&right=local.tafayu)
- [Railway](https://railway.com/)
- [Github com documentação: Biblioteca springdoc-openapi](https://github.com/springdoc/springdoc-openapi) 
- [Java-Oracle: Downloads](https://www.oracle.com/br/java/technologies/downloads/)
- [Flaticon](https://www.flaticon.com/)

  📎 Link do curso: [DIO.me](https://web.dio.me/home) 

