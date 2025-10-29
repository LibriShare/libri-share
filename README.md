# LibriShare

## Sobre o Projeto

O LibriShare é uma plataforma de gerenciamento e compartilhamento de livros. O objetivo é permitir que os usuários se conectem, cataloguem suas bibliotecas pessoais e descubram novos livros.

A plataforma foi projetada para incluir funcionalidades como:

* **Gestão de Biblioteca Pessoal:** Organização de livros em categorias como "Lendo Agora" , "Livros Lidos" e "Lista de Desejos".
* **Adição de Livros:** Múltiplos métodos para adicionar livros, incluindo busca online, escaneamento de ISBN e cadastro manual.
* **Gerenciamento de Empréstimos:** Funcionalidade para registrar e controlar empréstimos de livros para amigos ou outros usuários.
* **Componente Social (LibriConnect):** Uma rede social interna onde os usuários podem ver um feed de atividades, participar de discussões e se conectar com amigos.
* **Perfis de Usuário:** Páginas de perfil detalhadas com estatísticas de leitura, atividade recente e configurações de privacidade.

## 🛠️ Ferramentas e Tecnologias

O projeto é construído com as seguintes tecnologias:

### Back-end
* **Java**
* **Spring Boot:** Utilizado para construir a API RESTful e gerenciar a lógica de negócios, conforme detalhado no diagrama UML do projeto.

### Front-end
* **v0.dev:** A interface do usuário (UI) foi prototipada e gerada utilizando a tecnologia do v0. Os protótipos podem ser vistos no arquivo `LibriShare.pdf`.

### Banco de Dados
* **PostgreSQL:** Sistema de gerenciamento de banco de dados relacional escolhido para armazenar os dados da aplicação.

### Infraestrutura e DevOps
* **Docker:** Utilizado para criar containers para a aplicação e seus serviços (como o banco de dados), facilitando o desenvolvimento e o deploy.

### Documentação
* **MkDocs:** Gerador de sites de documentação estática.
* **Material for MkDocs:** Tema utilizado para a documentação.

## 🔗 Links Relevantes

* **[Design Sprint (Miro)](https://miro.com/app/board/uXjVJLIyOmo=/)**: Board do Miro contendo as fases de ideação, benchmarking (Good Reads, Skoob, Libby) e design sprint do projeto.
* **[Protótipo de Front-end (v0.dev)](https://v0.app/chat/libri-share-platform-design-msPJcnG8O41?b=b_qAcFelQOQEo&f=1)**: Chat de desenvolvimento e prototipação da interface do usuário na plataforma v0.
* **[Diagrama UML (Back-end)](DiagramaUML_V1.png)**: Diagrama de classes com os métodos do back-end, mostrando entidades como `User`, `Book`, `Loan` e `Post`.

---

## Equipe

<div class="team-grid">
  <div class="team-member">
    <a href="https://github.com/BiancaPatrocinio7" target="_blank" rel="noopener">
      <img src="https://github.com/BiancaPatrocinio7.png" alt="Foto de Bianca Patrocínio Castro">
      <p>Bianca<br>Patrocínio Castro</p>
    </a>
  </div>
</div>

---

## Histórico de Versões

| Versão | Data       | Descrição                                           | Autor                                           | Revisor |
| :----: | ---------- | --------------------------------------------------- | ----------------------------------------------- | ------- |
|  `1.0` | 28/10/2025 | Criação da estrutura inicial da documentação.       | Bianca Patrocínio                               | Gemini  |


---
