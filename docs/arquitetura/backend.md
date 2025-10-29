# Arquitetura Back-end

O back-end do LibriShare é uma API RESTful construída em Java com o framework Spring Boot, conectada a um banco de dados PostgreSQL.

## Diagrama de Classes (UML)

O diagrama abaixo ilustra as principais entidades do sistema e seus relacionamentos:

![Diagrama de Classes UML do Back-end](../assets/images/DiagramaUML_V1.png)

<font size="3"><p style="text-align: center">Fonte: Autoria própria (2025)</p></font>

### Entidades Principais

* **User:** Representa o usuário da plataforma. Contém informações pessoais (nome, email, hash da senha) e de endereço (para empréstimos). O usuário `cria` Posts e `possui na biblioteca` UserBooks.
* **Book:** A entidade de livro "global", com dados imutáveis como título, autor, ISBN, etc..
* **UserBook:** A classe chave que representa "um livro na biblioteca de um usuário específico". É aqui que são armazenados os dados de leitura do usuário, como status (`ReadingStatus`), notas privadas, avaliação e progresso (página atual).
* **Loan:** Representa um empréstimo. Está associado a um `UserBook` (o que foi emprestado) e a um `User` (quem emprestou). Contém dados como o nome do mutuário e as datas de empréstimo/devolução.
* **Post / Comment:** Entidades que alimentam o lado social (LibriConnect). Um `User` `cria` um `Post` (que pode ser uma `REVIEW`, `STATUS_UPDATE`, etc.) e outros usuários podem `escrever` `Comments`.