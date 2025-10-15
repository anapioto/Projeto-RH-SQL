# 🏢 Projeto de Banco de Dados: Gestão de Recursos Humanos (RH)

## 📝 Sobre o Projeto

Este projeto consiste na criação e manipulação de um Banco de Dados Relacional para um sistema de Gerenciamento de Recursos Humanos (RH) e Vendas. Foi desenvolvido como exercício prático para demonstrar proficiência em Modelagem de Dados e Consultas SQL complexas.

### 🎯 Objetivos

1.  **Modelagem de Dados:** Estruturar um banco de dados que represente entidades de uma empresa (Departamentos, Colaboradores, Comissões, Endereços, Benefícios e Avaliações).
2.  **Implementação SQL:** Utilizar DDL e DML para criar, popular e atualizar as tabelas.
3.  **Consultas Avançadas:** Desenvolver consultas SQL complexas usando **Subconsultas** e **Funções de Agregação** para extrair informações de negócio relevantes.

### 🛠️ Tecnologias Utilizadas

* **Banco de Dados:** Oracle SQL / PLSQL (Scripts compatíveis com a maioria dos SGBDs).
* **Linguagem:** SQL.

---

## 📚 Modelagem do Banco de Dados

O projeto é baseado em um esquema com as seguintes entidades e seus respectivos relacionamentos:

| Entidade | Descrição | Chaves |
| :--- | :--- | :--- |
| `departamento` | Unidades da empresa (Nome, País, Região, Endereço). | `id_departamento` (PK) |
| `colaborador` | Dados dos funcionários (Nome, Função, Salário, Data de Contratação). | `id_colaborador` (PK), `id_departamento` (FK) |
| `comissao` | Registros de pagamentos de comissão por vendas. | `id_pagamento` (PK), `id_colaborador` (FK), `id_departamento` (FK) |
| `endereco` | Detalhes de localização dos departamentos. | `id_endereco` (PK), `id_departamento` (FK) |
| `Beneficio` | Benefícios concedidos aos colaboradores (Vale Refeição, Plano de Saúde, etc.). | `id_beneficio` (PK), `id_colaborador` (FK) |
| `Avaliacao_desempenho` | Registro de performance dos colaboradores (Pontuação, Comentários). | `id_avaliacao` (PK), `id_colaborador` (FK) |

---

## 🔎 Análise de Dados: As 10 Consultas SQL

O arquivo principal contém uma seção dedicada a 10 consultas de análise de dados, todas utilizando subconsultas.

| Nº | Descrição da Consulta | Destaque Técnico |
| :--- | :--- | :--- |
| 1 | Colaboradores que recebem um **Vale Refeição** acima de R$ 300,00. | Subconsulta e filtro (`WHERE >`). |
| 2 | Colaboradores com **Avaliação de Desempenho** acima de 8 na sua última avaliação. | Subconsulta correlacionada e `MAX()`. |
| 3 | Departamentos localizados no **Brasil**. | Filtro com `LIKE` (país). |
| 4 | Colaboradores que receberam **Comissão** com taxa superior a 10%. | `SELECT DISTINCT` e Subconsulta. |
| 7 | Colaboradores com **Pontuação de Avaliação** acima da média geral. | Subconsulta com `AVG()`. |
| 9 | Departamentos com **Salário** médio de seus colaboradores acima da média geral da empresa. | Subconsulta com `AVG()` no filtro. |
| 10 | Departamentos que oferecem **Plano de Saúde** com valor acima de R$ 500,00. | Subconsulta e junção implícita de 3 tabelas. |
| *e outras...* | | |

---

## ⚙️ Como Reproduzir o Projeto

1.  **Ambiente:** Utilize um cliente SQL (como SQL Developer, DBeaver) ou o próprio SQL Plus/Terminal para se conectar ao seu SGBD.
2.  **Execução:** Execute o conteúdo do arquivo `atividadeaula8.sql` na ordem em que ele se apresenta:
    * Criação das tabelas (`CREATE TABLE`).
    * Inserção dos dados iniciais (`INSERT INTO`).
    * Alterações de Estrutura (`ALTER TABLE`).
    * Inserções e Atualizações finais (`INSERT INTO`, `UPDATE`).
    * Execução das 10 consultas (`SELECT`).
