# <h1 align="center"><img width="64" height="64" alt="desafio" src="https://github.com/user-attachments/assets/c6455b8f-1c5a-4775-8407-b8515e06ad3c" /> Desafio: Lab Publicando Sua API REST na Nuvem Usando Spring Boot 3 e Java 17</h1>
Este repositório reúne os principais aprendizados adquiridos durante o **Bootcamp GFT - Desenvolvimento Java com IA - Curso: Banco de Dados, Padrões de Projeto e APIs com Spring Boot** da plataforma DIO.me. 
Este projeto foi desenvolvido como parte do desafio da Digital Innovation One (DIO), com o objetivo de aplicar os principais padrões de projeto na construção de uma API REST moderna utilizando **Java 17** e **Spring Boot 3**, aplicando boas práticas de arquitetura, documentação e persistência de dados.

---

## <img width="64" height="64" alt="missao" src="https://github.com/user-attachments/assets/97d06f58-1280-4c95-8b54-9d4035e6c3a9" /> Sobre o Desafio
O desafio proposto é uma iniciativa educacional que conecta desenvolvedores com o mercado financeiro, promovendo capacitação prática com tecnologias modernas. 
Não cheguei a fazer o deploy na nuvem, mas assim que o fizer, atualizo o repostório!

O projeto simula uma API de uma conta bancária simples com recursos como:
- Cartões do Cliente
- Notícias
- Feature
- Usuários

## <img width="64" height="64" alt="roda-dentada" src="https://github.com/user-attachments/assets/6bc5d336-0bc7-4431-a775-17fde288de1d" /> Tecnologias Utilizadas

- **Java 17**
- **Spring Boot 3**
- **Spring Data JPA**
- **H2 Database** (ambiente de desenvolvimento)
- **PostgreSQL** (ambiente de produção)
- **Springdoc OpenAPI (Swagger UI)** – documentação interativa
- **Gradle** – gerenciamento de dependências
- **IntelliJ IDEA** – ambiente de desenvolvimento
- **Railway** – deploy na nuvem (opcional)

## <img width="64" height="64" alt="project-management" src="https://github.com/user-attachments/assets/1cd4f3ee-56b9-4735-a087-cb0a95174853" /> Criação do Projeto
O projeto foi gerado via [Spring Initializr](https://start.spring.io/) com as seguintes dependências:

- Spring Web
- Spring Data JPA
- PostgreSQL Driver
- H2 Database
- Spring Boot DevTools
- Spring Boot Test

## <img width="64" height="64" alt="estrutura-hierarquica" src="https://github.com/user-attachments/assets/c2502579-1a1e-4300-8228-1ff36269bf93" /> Diagrama de Classes

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

## <img width="64" height="64" alt="gerenciamento-de-banco-de-dados" src="https://github.com/user-attachments/assets/8881bd9e-dd6f-4eaa-8a69-bd30d55b0833" /> Banco de Dados

Durante o desenvolvimento, foi utilizado o **H2 Database**, um banco em memória leve e de fácil visualização via console:

- Console: `http://localhost:8080/h2-console`
- JDBC URL: `jdbc:h2:mem:sdw2025`
- Usuário: `sdw2025`
- Senha: *(em branco)*

Para produção, o projeto está preparado para uso com **PostgreSQL**, com configuração via `application-prod.yml`.

## <img width="64" height="64" alt="documentacao" src="https://github.com/user-attachments/assets/cb091698-bf18-4c04-87c7-49e36f72691e" /> Documentação da API

A documentação interativa da API é gerada automaticamente com **Swagger UI**:

- Acesse: `http://localhost:8080/swagger-ui/index.html`
- Endpoint da especificação: `/v3/api-docs`

## <img width="64" height="64" alt="estrutura" src="https://github.com/user-attachments/assets/eaf9bd37-dec8-4c0a-965b-3aa82aa6b6d9" /> Estrutura do Projeto

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

## <img width="64" height="64" alt="funcional" src="https://github.com/user-attachments/assets/83cbb8ba-bf5b-487e-8ff8-322d2caf2396" /> Funcionalidades

- Cadastro de usuários com validação de número de conta
- Consulta de usuário por ID
- Tratamento global de exceções com `@RestControllerAdvice`
- Documentação automática com Swagger
- Deploy preparado para ambientes como Railway

## <img width="64" height="64" alt="laboratorio-virtual" src="https://github.com/user-attachments/assets/1d3bb302-0cdd-4883-a7df-e1528cb3fcbb" /> Testes
Os testes são executados com JUnit 5 e Spring Boot Starter Test:
```bash
./gradlew test
```
## <img width="64" height="64" alt="tecnologia" src="https://github.com/user-attachments/assets/6e034866-edcb-46b8-af5c-86c5b8aab59a" /> Deploy
O projeto pode ser facilmente publicado na nuvem com Railway, utilizando o Procfile já incluído:

```
web: java -jar build/libs/santander-dev-week-2025-0.0.1-SNAPSHOT.jar
```

## <img width="64" height="64" alt="desenvolvedor" src="https://github.com/user-attachments/assets/97964c8d-d192-406d-8b10-a26e80f281ec" /> Desenvolvedora
Izaura TM - responsável pelo projeto.

## <img width="64" height="64" alt="ajuda-do-bot" src="https://github.com/user-attachments/assets/d0d14d08-d507-43ed-bab3-b71abdf594c1" /> Contribuições
Sinta-se à vontade para abrir issues ou enviar pull requests com melhorias, sugestões ou novas funcionalidades!

> Este conteúdo faz parte do projeto **Publicando Sua API REST na Nuvem Usando Spring Boot 3, Java 17 e Railway - Laboratório** da plataforma DIO.me.

---

 ## <img width="32" height="32" alt="certo" src="https://github.com/user-attachments/assets/ab1fe443-b716-436a-b618-11b794a03a93" /> Links de Referência:  
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


