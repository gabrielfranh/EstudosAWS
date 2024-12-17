Aplicação Monolítica: 
- Aplicação com componentes altamente acoplados, componentes como: Banco de dados, servers, interface de usuário, etc.
- Se um componente falhar, outros irão e possivelmente todo o sistema
Arquitetura de Microsserviços:
- Aplicação com componentes desacoplados, ou seja, independentes
- Caso um serviço venha a falhar, os outros continuarão seu funcionamento normal


#### Amazon Simple Queue Service (SQS)
Sistema de filas, proporcionando comunicação assíncrona de mensagens entre aplicações e serviços.
Um serviço publica a mensagem e outro recebe, caso o receptor esteja fora, a mensagem é armazenada na fila até ser consumida
Utiliza o sistema FIFO (First in, first out, sistema de fila)
Limitação: As cargas de mensagem podem conter até 256 KB de texto em qualquer formato.
**Retenha as mensagens nas filas por até 14 dias.**



#### Amazon Simple Notification Service
Sistema de Pub/Sub, onde um publicador envia a mensagem por tópico, podendo ser consumida por inscritos
Receptores da mensagem podem ser serviços, AWS Lambda, endpoints, SQS, Webhooks, phone push, etc.
Cada mensagem pode conter, no máximo, 256 KB de dados
