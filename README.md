# Projeto de Ordem de Serviço Automotiva

Este projeto define o modelo de banco de dados para um sistema de ordem de serviço em um contexto automotivo. O objetivo é gerenciar clientes, veículos, produtos, armazenamento de peças e serviços realizados, incluindo consertos e revisões.

## Visão Geral

O banco de dados foi modelado para suportar a gestão de ordens de serviço automotivas, com foco no controle de produtos, estoque, clientes, equipe de mecânicos, revisões e consertos. Esse modelo permite a rastreabilidade de ordens de serviço, o gerenciamento de equipes e o acompanhamento de serviços prestados ao cliente, assegurando consistência e integridade dos dados.

### Ferramenta Utilizada

O diagrama entidade-relacionamento (ER) foi criado utilizando o **MySQL Workbench**.

### Diagrama ER

![Diagrama ER - Ordem de Serviço Automotiva](Modelo_conceitual.png)

## Estrutura do Banco de Dados

### Entidades e Relacionamentos

1. **Cliente**
   - Representa os clientes que solicitam serviços.
   - **Atributos**:
     - `idCliente`: Identificador único do cliente.
     - `Nome`: Nome do cliente.
     - `Endereço`: Endereço do cliente.
     - `Contato`: Informação de contato do cliente.

2. **Ordem de Serviço**
   - Registro de uma ordem de serviço associada a um cliente.
   - **Atributos**:
     - `idOrdem de Serviço`: Identificador único da ordem de serviço.
     - `Cliente_idCliente`: Identificador do cliente associado.
     - `Data de Criação`: Data de criação da ordem de serviço.

3. **Produto**
   - Representa peças e produtos disponíveis para uso nos serviços.
   - **Atributos**:
     - `idProduto`: Identificador único do produto.
     - `Nome do Produto`: Nome da peça ou produto.
     - `Descrição`: Descrição do produto.
     - `Valor`: Preço do produto.

4. **Armazenagem**
   - Local onde os produtos são estocados.
   - **Atributos**:
     - `idArmazen`: Identificador único do local de armazenamento.
     - `Local`: Descrição do local de armazenamento.

5. **Armazen_has_Produto**
   - Relaciona produtos ao local de armazenamento e quantifica o estoque.
   - **Atributos**:
     - `Armazem_idArmazen`: Identificador do local de armazenamento.
     - `Produto_idProduto`: Identificador do produto.
     - `Quantidade`: Quantidade disponível em estoque.

6. **Concerto do Veículo**
   - Registro de um conserto realizado em um veículo.
   - **Atributos**:
     - `idConcerto do Veículo`: Identificador único do conserto.
     - `Ordem de Serviço_idOrdem de Serviço`: Identificador da ordem de serviço associada.
     - `Ordem de Serviço_Cliente_idCliente`: Identificador do cliente.
     - `Descrição do Problema`: Descrição do problema do veículo.

7. **Revisão do Veículo**
   - Registro de uma revisão feita no veículo.
   - **Atributos**:
     - `idRevisão do Veículo`: Identificador único da revisão.
     - `Ordem de Serviço_idOrdem de Serviço`: Identificador da ordem de serviço associada.
     - `Ordem de Serviço_Cliente_idCliente`: Identificador do cliente.
     - `Descrição da Revisão`: Descrição da revisão realizada.
     - `Valor`: Custo da revisão.

8. **Seleção de Equipe**
   - Relaciona mecânicos aos serviços executados.
   - **Atributos**:
     - `idEquipMecanicos`: Identificador único da equipe.
     - `Concerto do Veículo_idConcerto do Veículo`: Identificador do conserto.
     - `Revisão do Veículo_idRevisão do Veículo`: Identificador da revisão.
     - `Descrição do serviço`: Detalhes do serviço realizado.
     - `Valor Serviço`: Custo do serviço.
     - `Data de Entrega`: Data de entrega do serviço.
     - `Seleção de Equipecol`: Informação adicional sobre a equipe.
     - `Produto_idProduto`: Identificador do produto utilizado no serviço.

9. **Mecânico**
   - Representa um mecânico que realiza os serviços.
   - **Atributos**:
     - `idMecanico`: Identificador único do mecânico.
     - `Nome`: Nome do mecânico.
     - `Cargo`: Cargo do mecânico.
     - `Data de Contratação`: Data de contratação do mecânico.
     - `Especialização`: Especialização do mecânico.
     - `EquipMecanicos_idEquipMecanicos`: Identificador da equipe a que o mecânico pertence.

### Relacionamentos

- **Cliente e Ordem de Serviço**: Um cliente pode ter várias ordens de serviço (1:N).
- **Ordem de Serviço e Produto**: A ordem de serviço pode usar vários produtos (N:M).
- **Armazenagem e Produto**: Define onde os produtos são armazenados e suas quantidades (1:N).
- **Concerto do Veículo e Ordem de Serviço**: Cada conserto está associado a uma ordem de serviço específica (1:1).
- **Revisão do Veículo e Ordem de Serviço**: Cada revisão está vinculada a uma ordem de serviço específica (1:1).
- **Seleção de Equipe e Mecânico**: Cada equipe de serviço é composta por vários mecânicos, e cada mecânico pode participar de várias equipes (N:M).

## Estrutura e Organização

Esta estrutura foi criada para permitir o gerenciamento eficiente de ordens de serviço automotivas, incluindo:

- Cadastro de clientes e produtos.
- Gerenciamento de estoque de peças.
- Registro e acompanhamento de ordens de serviço, incluindo consertos e revisões.
- Atribuição de mecânicos e equipes para execução de serviços.

## Como Utilizar

Este modelo pode ser implementado em sistemas de gerenciamento de banco de dados como MySQL ou PostgreSQL. Cada entidade e relacionamento foi projetado para garantir consistência e facilitar a expansão futura do sistema.



<div align="center"> 
  <a href = "mailto:roberto.smj.ti@gmail.com" target="_blank"><img src="https://img.shields.io/badge/Contato-mail-8B89CC?style=for-the-badge&logo=protonmail&logoColor=white" target="_blank"></a>
  <a href="https://www.linkedin.com/in/roberto-smj/" target="_blank"><img src="https://img.shields.io/badge/-LinkedIn-%230077B5?style=for-the-badge&logo=linkedin&logoColor=white" target="_blank"></a> 
</div>