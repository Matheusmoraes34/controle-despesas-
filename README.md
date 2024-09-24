# controle-despesas-
Sistema de controle de despesas em Java

# Sistema de Controle de Despesas

## Descrição do Projeto
Este sistema de controle de despesas foi desenvolvido para permitir o gerenciamento de despesas e pagamentos de forma eficiente. O sistema foi construído em Java, utilizando princípios de Programação Orientada a Objetos (POO) e conectando-se a um banco de dados MySQL via JDBC.

## Funcionalidades
1. **Entrar Despesa**: Inserção de despesas, incluindo descrição, valor, data de vencimento e categoria.
2. **Anotar Pagamento**: Registro de pagamentos para despesas específicas.
3. **Listar Despesas**: Visualização de despesas filtradas por status (pagas, pendentes) e categorias.
4. **Gerenciar Tipos de Despesa**: Adição, edição e exclusão de tipos de despesa, armazenados em um arquivo de texto.
5. **Gerenciar Usuários**: Cadastro, edição e listagem de usuários, com criptografia de senhas.
6. **Persistência de Dados**: Utiliza arquivos de texto e banco de dados MySQL para armazenar dados de despesas e usuários.

## Estrutura do Projeto
O projeto segue uma estrutura organizada de pacotes:



### Documentação das Classes

#### **Classe `Despesa`**

A classe `Despesa` é abstrata e contém os atributos comuns a todas as despesas, como `descricao`, `valor`, `dataVencimento` e `categoria`. Ela é herdada por outras classes específicas, como `DespesaTransporte`.

- **Atributos**:
  - `descricao`: String
  - `valor`: double
  - `dataVencimento`: Date
  - `categoria`: String
  
- **Métodos**:
  - `exibirDetalhes()`: Método abstrato que será implementado nas subclasses.

#### **Classe `DespesaTransporte`**

Esta classe herda de `Despesa` e representa uma despesa de transporte.

- **Atributos**: Herda os atributos de `Despesa`.
- **Métodos**:
  - `exibirDetalhes()`: Sobrescreve o método para exibir os detalhes específicos da despesa de transporte.

#### **Classe `Pagamento`**

Gerencia os pagamentos realizados para despesas.

- **Atributos**:
  - `dataPagamento`: Date
  - `valorPago`: double
  - `despesa`: Despesa

- **Métodos**:
  - `exibirDetalhesPagamento()`: Exibe detalhes do pagamento realizado.

#### **Classe `Usuario`**

Gerencia usuários e realiza a criptografia de suas senhas.

- **Atributos**:
  - `login`: String
  - `senhaCriptografada`: String

- **Métodos**:
  - `criptografarSenha(senha)`: Método privado que utiliza o algoritmo SHA-256 para criptografar senhas.

#### **Classe `ConexaoBD`**

Gerencia a conexão com o banco de dados MySQL.

- **Métodos**:
  - `conectar()`: Retorna a conexão JDBC com o banco de dados.

#### **Classe `DespesaDAO`**

Realiza operações de banco de dados para despesas.

- **Métodos**:
  - `inserirDespesa(Despesa despesa)`: Insere uma despesa no banco de dados.

#### **Classe `TipoDespesaDAO`**

Gerencia os tipos de despesa, armazenando-os em arquivos de texto.

- **Métodos**:
  - `salvarTipoDespesa(String tipo)`: Escreve um tipo de despesa no arquivo de texto `tipos_despesa.txt`.

### Tecnologias Utilizadas
- **Java**: Linguagem principal para implementação das regras de negócio.
- **MySQL**: Banco de dados relacional para armazenar despesas e usuários.
- **JDBC**: Para conexão e manipulação de dados no MySQL.
- **HTML/CSS**: Interface web básica para interação do usuário.
- **XAMPP**: Ferramenta para gerenciar o servidor MySQL local.

### Como Executar o Projeto
1. Clone este repositório:
   ```bash
   
