# TabelaFipe

Uma aplicação Java para consulta de informações da Tabela Fipe, integrada com a API Fipe Online.

## Descrição do Projeto

O projeto **TabelaFipe** é uma aplicação desenvolvida em Java, utilizando o framework Spring Boot, que permite aos usuários consultar dados da Tabela Fipe de forma interativa. Através de um console simples, é possível buscar informações sobre marcas, modelos e anos de veículos (carros, motos e caminhões), obtendo os valores de mercado correspondentes. A aplicação se conecta à API Fipe Online para buscar e apresentar os dados atualizados.

## Funcionalidades

*   **Consulta de Marcas:** Permite listar as marcas disponíveis para um tipo de veículo (carro, moto ou caminhão).
*   **Consulta de Modelos:** Após selecionar uma marca, exibe os modelos de veículos associados.
*   **Consulta por Ano:** Para um modelo específico, apresenta os anos de fabricação disponíveis e os respectivos valores da Tabela Fipe.
*   **Filtro por Termo:** Possibilidade de filtrar modelos de veículos por um termo de busca.

## Tecnologias Utilizadas

*   **Java 17:** Linguagem de programação principal.
*   **Spring Boot:** Framework para desenvolvimento rápido de aplicações Java.
*   **Maven:** Ferramenta de automação de build e gerenciamento de dependências.
*   **Jackson Databind:** Biblioteca para serialização e desserialização de JSON.
*   **API Fipe Online:** API externa utilizada para obter os dados da Tabela Fipe.

## Estrutura do Projeto

O projeto segue a estrutura padrão de um projeto Spring Boot Maven:

```
.mvn/
src/
├── main/
│   ├── java/
│   │   └── br/com/eduuardo1st/TabelaFipe/
│   │       ├── model/             # Classes de modelo para estruturar os dados da Fipe (Dados, Modelos, Veiculo)
│   │       ├── principal/         # Lógica principal da aplicação e interação com o usuário (Classe Principal)
│   │       └── service/           # Lógica de negócio e consumo da API (Classe ConsumoApi, ConverteDados)
│   └── resources/         # Arquivos de configuração e recursos da aplicação
├── test/                  # Testes unitários e de integração
pom.xml                    # Arquivo de configuração do Maven
```

### Principais Classes:

*   `TabelaFipeApplication.java`: Classe principal do Spring Boot que inicializa a aplicação.
*   `Principal.java`: Contém a lógica de interação com o usuário via console, exibindo menus e processando as entradas para realizar as consultas.
*   `ConsumoApi.java`: Responsável por fazer as requisições HTTP à API Fipe Online e obter os dados em formato JSON.
*   `ConverteDados.java`: Realiza a conversão dos dados JSON recebidos da API para objetos Java.
*   `Dados.java`, `Modelos.java`, `Veiculo.java`: Classes de modelo (records) que representam a estrutura dos dados retornados pela API Fipe.

## Como Usar

Para executar a aplicação localmente, siga os passos abaixo:

### Pré-requisitos

*   Java Development Kit (JDK) 17 ou superior instalado.
*   Maven instalado.

### Compilação e Execução

1.  **Clone o repositório:**
    ```bash
    git clone https://github.com/eduuardo1st/TabelaFipe.git
    ```
2.  **Navegue até o diretório do projeto:**
    ```bash
    cd TabelaFipe
    ```
3.  **Compile o projeto usando Maven:**
    ```bash
    ./mvnw clean install
    ```
4.  **Execute a aplicação:**
    ```bash
    java -jar target/TabelaFipe-0.0.1-SNAPSHOT.jar
    ```
    Ou, se estiver usando um IDE como IntelliJ IDEA ou Eclipse, execute a classe `TabelaFipeApplication.java` diretamente.

### Interagindo com a Aplicação

Após a execução, a aplicação apresentará um menu no console. Siga as instruções para escolher o tipo de veículo (carro, moto ou caminhão), pesquisar marcas, modelos e anos, e visualizar os valores da Tabela Fipe.

## API Fipe Online

Esta aplicação utiliza a API pública da Fipe Online para obter os dados. A URL base da API é: `https://fipe.parallelum.com.br/api/v2/`.

## Contribuição

Contribuições são bem-vindas! Se você deseja melhorar este projeto, siga os passos:

1.  Faça um fork do repositório.
2.  Crie uma nova branch (`git checkout -b feature/sua-feature`).
3.  Faça suas alterações e commit (`git commit -am 'Adiciona nova feature'`).
4.  Envie para a branch (`git push origin feature/sua-feature`).
5.  Abra um Pull Request.

## Licença

Este projeto está licenciado sob a licença MIT. Consulte o arquivo `LICENSE` para mais detalhes. (Assumindo licença MIT, caso contrário, ajustar conforme necessário).
