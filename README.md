**Helpdesk Microservices**  

Ambiente local com Docker Compose para executar os serviços do projeto Helpdesk.  
Este ambiente sobe os seguintes containers:  
- MySQL  
- RabbitMQ  
- Helpdesk API  
- Notificação Service

  
**Arquitetura**  
Fluxo principal da aplicação:  
Usuário cria um chamado  
         ↓  
 helpdesk-api salva o chamado no MySQL  
         ↓  
 helpdesk-api publica um evento no RabbitMQ  
         ↓  
 notificacao-service consome o evento  
         ↓  
 notificacao-service processa a notificação  
   
## Como subir o ambiente  
   
Este Docker Compose utiliza imagens publicadas no Docker Hub.  
   
Imagens utilizadas:  
   
- `lreis393/helpdesk-api:dev`  
- `lreis393/notificacao-service:dev`  
   
Para baixar as imagens mais recentes:  
   
```bash  
docker compose pull  
