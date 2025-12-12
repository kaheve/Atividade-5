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

## Diagrama de Classes

```mermaid
flowchart LR

%% Diagrama de Classes - Clube do Livro SJBV
classDiagram

    class Membro {
        +int id
        +String nome
        +String email
        +String telefone
        +verificarPendencias() boolean
        +obterEmprestimos() List~Emprestimo~
    }

    class Livro {
        +int id
        +String titulo
        +String autor
        +String isbn
        +boolean disponivel
        +verificarDisponibilidade() boolean
        +reservar() boolean
    }

    class Emprestimo {
        +int id
        +Date dataEmprestimo
        +Date dataDevolucaoPrevista
        +Date dataDevolucaoReal
        +boolean devolvido
        +calcularAtraso() int
    }

    Membro "1" --> "0..*" Emprestimo : possui
    Livro "1" --> "0..*" Emprestimo : éReferenciadoEm
    Emprestimo --> Membro : pertenceA
    Emprestimo --> Livro : referencia

---

## Diagrama de Casos de Uso

```mermaid
flowchart LR

actorM((Membro))
actorA((Administrador))

actorM --- UC1[(Consultar Catálogo)]
actorM --- UC2[(Solicitar Empréstimo)]
actorM --- UC3[(Devolver Livro)]
actorM --- UC4[(Ver Meus Empréstimos)]

actorA --- UC5[(Cadastrar Livro)]
actorA --- UC6[(Atualizar Livro)]
actorA --- UC7[(Gerenciar Membros)]
actorA --- UC8[(Ver Relatórios de Empréstimos)]

---
