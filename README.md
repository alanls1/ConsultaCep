# Consulta de CEP com Spring Web

Este projeto é uma aplicação Java utilizando o framework Spring Web para realizar consultas de CEPs (Códigos de Endereçamento Postal) através de uma API externa. 

## Tecnologias Utilizadas

- Java 11
- Spring Boot 2.6
- Spring Web
- RestTemplate
- Maven

## Funcionalidades

- Consultar informações de endereço a partir de um CEP.
- Integrar-se com uma API externa para obter os dados do endereço.

## Pré-requisitos

- Java 11 ou superior
- Maven 3.6 ou superior

## Instalação e Execução

1. Clone o repositório:
    ```sh
    git clone https://github.com/seu-usuario/nome-do-repositorio.git
    cd nome-do-repositorio
    ```

2. Compile e execute a aplicação:
    ```sh
    mvn clean install
    mvn spring-boot:run
    ```

3. A aplicação estará disponível em `http://localhost:8080`.

## Endpoints

### Consultar CEP

- **URL:** `/cep/{cep}`
- **Método:** `GET`
- **Parâmetros:**
  - `cep` (string): O CEP a ser consultado.

- **Exemplo de Requisição:**
    ```sh
    curl -X GET http://localhost:8080/cep/01001000
    ```

- **Exemplo de Resposta:**
    ```json
    {
      "cep": "01001-000",
      "logradouro": "Praça da Sé",
      "complemento": "lado ímpar",
      "bairro": "Sé",
      "localidade": "São Paulo",
      "uf": "SP",
      "ibge": "3550308",
      "gia": "1004",
      "ddd": "11",
      "siafi": "7107"
    }
    ```

## Estrutura do Projeto

```plaintext
src
├── main
│   ├── java
│   │   └── com
│   │       └── exemplo
│   │           └── consultaCep
│   │               ├── CepResultDTO.java
│   │               ├── ConsultaCepAPI.java
│   │                   
│   └── resources
│       └── application.properties
└── test
    └── java
        └── com
            └── exemplo
                └── consultaCep
                    └── ConsultaCepApplicationTests.java
