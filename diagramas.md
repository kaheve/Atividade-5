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

