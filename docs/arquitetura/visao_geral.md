# Visão Geral da Arquitetura

O LibriShare segue uma arquitetura cliente-servidor desacoplada (RESTful), composta por um **Frontend SPA** e um **Backend Monolítico Modular**.

## Diagrama de Contêineres (C4 Nível 2)

```mermaid
graph TD
    User((Usuário))
    
    subgraph "Frontend (Vercel)"
        NextJS[Next.js App\n(React + TypeScript)]
    end
    
    subgraph "Backend (Render)"
        API[Spring Boot Monolith\n(Java 17)]
        
        subgraph "Módulos Internos"
            UserMod[Módulo User]
            BookMod[Módulo Book]
            LoanMod[Módulo Loan]
        end
    end
    
    subgraph "Persistência"
        DB[(PostgreSQL)]
    end
    
    subgraph "Externo"
        OpenLib[OpenLibrary API]
    end

    User -->|HTTPS| NextJS
    NextJS -->|JSON/REST| API
    API -->|Validação/Lógica| UserMod
    API -->|Validação/Lógica| BookMod
    API -->|Validação/Lógica| LoanMod
    API -->|JDBC| DB
    API -->|Metadata| OpenLib


## Fluxo de Dados

1.  **Requisição:** O usuário interage com a interface (Next.js).
2.  **API Call:** O Frontend envia requisições para o Backend (ex: `GET /api/v1/books`).
3.  **Processamento:** O Spring Boot recebe a requisição, valida regras de negócio e acessa o banco.
4.  **Integração Externa:** Para capas de livros, o sistema consulta a API pública da OpenLibrary.
5.  **Persistência:** Dados críticos (usuários, empréstimos, histórico) são salvos no PostgreSQL.

<!-- end list -->

````

#### `docs/arquitetura/backend.md`

```markdown
# Arquitetura do Backend

O Backend é construído em **Java 17** com **Spring Boot 3**, seguindo os princípios de *Clean Architecture* simplificada e *Domain-Driven Design (DDD)* na separação de módulos.

## Estrutura de Pacotes

A aplicação é modularizada por domínio funcional:

* `modules/user`: Autenticação, perfil e gestão de usuários.
* `modules/book`: Catálogo global de livros (metadados).
* `modules/library`: Vínculo entre usuário e livro (status, avaliação).
* `modules/loan`: Lógica de empréstimos e devoluções.
* `modules/history`: Logs de auditoria e linha do tempo.

## Modelo de Dados (ER)

O banco de dados PostgreSQL é gerenciado via **Flyway**. Abaixo o esquema relacional atual:

```mermaid
erDiagram
    USERS ||--o{ USER_BOOKS : possui
    BOOKS ||--o{ USER_BOOKS : catalogado_como
    USER_BOOKS ||--o{ LOANS : empresta
    USERS ||--o{ HISTORY : gera

    USERS {
        Long id PK
        String email
        String password_hash
        String first_name
        Int reading_goal
    }

    BOOKS {
        Long id PK
        String title
        String isbn
        String cover_url
    }

    USER_BOOKS {
        Long id PK
        Enum status "READ, READING, TO_READ"
        Int current_page
        Int rating
    }

    LOANS {
        Long id PK
        String borrower_name
        Date due_date
        Enum status "ACTIVE, RETURNED"
    }
````

## Segurança

  * **Autenticação:** Baseada em ID de sessão (MVP) e preparada para JWT.
  * **Senhas:** Hash utilizando `BCryptPasswordEncoder`.
  * **CORS:** Configurado para aceitar origens específicas (Vercel/Localhost).

<!-- end list -->

````