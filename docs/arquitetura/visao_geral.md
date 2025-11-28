# Visão Geral da Arquitetura

O LibriShare segue uma arquitetura cliente-servidor desacoplada (RESTful), composta por um **Frontend SPA** e um **Backend Monolítico Modular**.

## Diagrama de Contêineres (C4 Nível 2)

Abaixo apresentamos a visão lógica dos contêineres e suas integrações.

![Diagrama de Arquitetura C4](../assets/images/arquiteturaFlow.svg)

<font size="3"><p style="text-align: center">Fonte: Autoria própria (2025)</p></font>


## Fluxo de Dados

1.  **Requisição:** O usuário interage com a interface (Next.js).
2.  **API Call:** O Frontend envia requisições para o Backend (ex: `GET /api/v1/books`).
3.  **Processamento:** O Spring Boot recebe a requisição, valida regras de negócio e acessa o banco.
4.  **Integração Externa:** Para capas de livros, o sistema consulta a API pública da OpenLibrary.
5.  **Persistência:** Dados críticos (usuários, empréstimos, histórico) são salvos no PostgreSQL.

