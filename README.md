# 📚 Clube do Livro SJBV — Diagramas UML

Este repositório contém a modelagem UML desenvolvida para o sistema **Clube do Livro SJBV**, como parte da atividade da disciplina de **Projeto e Desenvolvimento de Sistemas (PDS)**.

O objetivo é transformar o processo manual de empréstimos de livros em um sistema informatizado, representando as estruturas e comportamentos por meio de diagramas UML.

---

## 📌 Objetivos da Modelagem
A modelagem visa:

- Identificar os **atores** e suas interações.
- Demonstrar o **fluxo interno** do processo de empréstimo.
- Mapear as **classes, atributos e relacionamentos** do sistema.

Os diagramas abaixo foram escritos em **Mermaid**, que o GitHub renderiza automaticamente como imagens.

---

'''mermaid
usecase
  :Usuário: as U
  :Sistema Clube do Livro: as S

  U --> (Criar Conta)
  U --> (Fazer Login)
  U --> (Explorar Livros)
  U --> (Adicionar Livro à Lista)
  U --> (Ler Resenhas)
  U --> (Escrever Resenha)

'''mermaid
flowchart TD
  A[Início] --> B[Usuário abre o aplicativo]
  B --> C{Está logado?}
  C -->|Sim| D[Redirecionar para tela inicial]
  C -->|Não| E[Exibir tela de login]
  E --> F[Usuário insere credenciais]
  F --> G{Credenciais válidas?}
  G -->|Sim| D
  G -->|Não| H[Mensagem de erro]
  H --> E
  D --> I[Usuário navega pelos livros]
  I --> J[Fim]

'''mermaid
sequenceDiagram
    participant U as Usuário
    participant A as Aplicativo
    participant S as Servidor

    U ->> A: Abrir aplicativo
    A ->> U: Exibir tela inicial
    U ->> A: Solicita login
    A ->> S: Enviar credenciais
    S ->> A: Validar e retornar resultado
    A ->> U: Login bem-sucedido

