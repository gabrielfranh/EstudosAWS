O **Amazon EKS** é um serviço gerenciado que facilita a execução, escalabilidade e operação de **clusters Kubernetes** na AWS. Ele elimina a necessidade de configurar, gerenciar e manter manualmente o **plano de controle** do Kubernetes, permitindo que você se concentre em seus **workloads** e aplicações.

**Gerenciamento do Plano de Controle**
- A AWS gerencia a alta disponibilidade, escalabilidade e patches do **control plane** do Kubernetes.

**Clusters Kubernetes Gerenciados**
- Suporte completo ao Kubernetes nativo, com API e ferramentas padrão **kubectl** e **Helm**.

**Opções de Execução para Workloads**
- **EC2**: Execute os **nós de trabalho** em instâncias EC2.
- **Fargate**: Execução serverless de pods sem gerenciar a infraestrutura subjacente.

**Escalabilidade**
- Use o **Cluster Autoscaler** para escalonar os nós e o **Horizontal Pod Autoscaler (HPA)** para escalonar os pods.

**Suporte a Kubernetes Padrão**
- Funciona com qualquer **plugin** ou **ferramenta** Kubernetes, como Prometheus, Grafana e Istio.


#### **Casos de Uso do EKS**

1. **Aplicações Nativas em Kubernetes**
    - Ideal para equipes que já utilizam **Kubernetes** como padrão de orquestração.
2. **Execução de Microserviços**
    - Facilita a criação, escalabilidade e gerenciamento de arquiteturas baseadas em microserviços.
3. **Modernização de Aplicações**
    - Migrar aplicações legadas para **containers** gerenciados no Kubernetes.
4. **Cargas de Trabalho Baseadas em CI/CD**
    - Integração com pipelines de **CI/CD** para automação de builds e deployments.
5. **IA/ML e Processamento de Dados**
    - Suporte a workloads como TensorFlow e Spark em containers.
6. **Aplicações Multi-Cloud ou Híbridas**
    - Kubernetes permite a portabilidade entre diferentes provedores de nuvem e ambientes on-premises.


![[EcsEks.png]]