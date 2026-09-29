# Helpdesk Microservices

Ambiente local com Docker Compose para executar os serviços do projeto Helpdesk.

Este ambiente sobe os seguintes containers:

- MySQL
- RabbitMQ
- Helpdesk API
- Notificação Service

## Arquitetura

Fluxo principal da aplicação:

```text
Usuário cria um chamado
        ↓
helpdesk-api salva o chamado no MySQL
        ↓
helpdesk-api publica um evento no RabbitMQ
        ↓
notificacao-service consome o evento
        ↓
notificacao-service processa a notificação
