# Padrão de Registro e Descoberta (Service Registry and Discovery):

Permite que os serviços se registrem em um registro central e descubram uns aos outros para comunicação.
Exemplos: Netflix Eureka, Consul, ZooKeeper.

# Padrão de Gateway de API (API Gateway):

Fornece um ponto de entrada único para os clientes acessarem os diferentes serviços.
Pode ser usado para autenticação, autorização, roteamento e balanceamento de carga.
Exemplos: Netflix Zuul, Kong, Apigee.

# Padrão de Roteamento de Mensagens (Messaging Routing):

Utiliza uma infraestrutura de mensagens assíncronas para rotear e transmitir eventos entre os serviços.
Pode ser usado para garantir a entrega confiável de mensagens, a integração de sistemas e a escalabilidade.
Exemplos: RabbitMQ, Apache Kafka.

# Padrão de Escalonamento Automático (Autoscaling):

Permite que os serviços se ajustem automaticamente com base na carga de trabalho para lidar com picos de tráfego.
Pode ser baseado em métricas como CPU, memória ou número de requisições.
Exemplos: Kubernetes Horizontal Pod Autoscaler (HPA), Amazon EC2 Auto Scaling.

# Padrão de Compensação (Compensation):

Lida com transações distribuídas, permitindo que as operações sejam desfeitas em caso de falha.
Pode ser usado para garantir a consistência em um ambiente distribuído.
Exemplos: Saga Pattern, TCC (Try-Confirm/Cancel).

# Padrão de Observabilidade (Observability):

Permite monitorar, coletar métricas e rastrear o desempenho dos serviços.
Ajuda na identificação e solução de problemas em um ambiente distribuído.
Exemplos: Prometheus, Grafana, Jaeger.

# Padrão de Gerenciamento de Configuração (Configuration Management):

Gerencia a configuração dos serviços, permitindo que sejam facilmente configurados e atualizados.
Pode incluir configuração externa, como variáveis de ambiente ou arquivos de configuração centralizados.
Exemplos: Spring Cloud Config, Consul, etcd.

# Decomposição de Serviços (Service Decomposition):

Discute estratégias para dividir um sistema monolítico em serviços independentes e coesos.

# Comunicação Síncrona (Synchronous Communication):

Explora padrões de comunicação direta entre serviços, como chamadas HTTP e RPC.
Comunicação Assíncrona (Asynchronous Communication):

Aborda padrões de comunicação baseados em mensagens assíncronas, como eventos e filas de mensagens.

# Banco de Dados por Serviço (Database per Service):
Discute a abordagem de ter um banco de dados dedicado para cada serviço, visando a independência e a escalabilidade.

# Event Sourcing:
Explora o padrão de design Event Sourcing, em que os eventos são a fonte de verdade para o estado dos serviços.

# CQRS (Command Query Responsibility Segregation):

Aborda a separação das operações de escrita (comandos) e leitura (consultas), permitindo otimizações específicas para cada caso.
# Descoberta de Serviço (Service Discovery):

Explora estratégias para localizar serviços dinamicamente em um ambiente distribuído.

# Roteamento de Requisições (Request Routing):

Discute técnicas de roteamento de solicitações para serviços, como balanceamento de carga e proxy reverso.

# Referencias / Observaçao: Muitos padroes deste plano foi retirado com base nas pesquisas feitas com ChatGPT outros foram retirados dos livros Microservices Patterns, Bulding microservices.

# SAGA Pattern

O Saga Pattern aborda o problema das transações que abrangem vários serviços em um ambiente distribuído, onde cada serviço tem sua própria fonte de dados e contexto transacional. Em um sistema monolítico, as transações geralmente são tratadas por meio de transações ACID (Atomicidade, Consistência, Isolamento e Durabilidade). No entanto, quando um sistema é dividido em serviços independentes, as transações distribuídas podem se tornar complexas.

No padrão Saga, uma transação de negócios complexa é dividida em etapas ou passos mais granulares, chamados de "ações". Cada ação representa uma alteração em um serviço específico. Quando uma ação é executada com sucesso, ela registra um evento indicando sua conclusão. No entanto, se ocorrer uma falha em uma ação, o padrão Saga possui mecanismos para reverter ou compensar as ações já executadas (processo conhecido como "compensação") e garantir que o sistema retorne a um estado consistente.

O Saga Pattern permite que transações complexas sejam tratadas de forma mais flexível em ambientes distribuídos. Em vez de uma transação monolítica, as transações são compostas por uma série de ações menores, cada uma com seu próprio mecanismo de reversão. Dessa forma, o padrão Saga ajuda a garantir a consistência global do sistema, mesmo em caso de falhas.




