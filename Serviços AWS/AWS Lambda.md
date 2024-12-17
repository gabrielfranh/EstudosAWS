#### Serverless:
- Recursos sem acesso à camada de infraestrutura, ou instâncias hosts da aplicação
- Todo o gerenciamento e escalabilidade é feito pela AWS automaticamente

#### **Principais Características do AWS Lambda**
**Modelo Serverless**
    - Nenhuma infraestrutura precisa ser gerenciada. A AWS gerencia provisionamento, escalabilidade e manutenção dos servidores.

**Execução Baseada em Eventos**
    - AWS Lambda é acionado por **eventos** de outros serviços AWS (ex.: S3, DynamoDB, API Gateway, SNS) ou aplicações externas.
    - **Exemplo**: Upload em um bucket S3 aciona a execução de uma função Lambda.

**Suporte a Vários Ambientes de Execução**
    Suporta diversas linguagens de programação, incluindo:
	    Node.js, Python, Java, C#, Go, Ruby, e Custom Runtimes

**Escalabilidade Automática**
    Lambda automaticamente escala **horizontalmente** para atender o volume de eventos, executando múltiplas instâncias da função simultaneamente.

**Cobrança Baseada no Uso**
    - Você paga apenas pelo tempo de execução (milissegundos) e pela quantidade de memória alocada.
    - **Exemplo**: Uma função que roda por 500ms com 512MB de memória gera custo somente para esse período.

**Gerenciamento de Estados Efêmeros**
    - Lambda não mantém estado entre execuções. Cada invocação é independente.
    - Para estados persistentes, utilize serviços como **Amazon S3**, **DynamoDB** ou **Step Functions**.

**Limites Configuráveis**
    
    - Tempo máximo de execução: 15 minutos.
    - Memória: 128MB a 10GB.
    - Tamanho máximo do pacote de código:** 50MB (direto) ou 10GB com container.
    - Conexões simultâneas: Pode ser limitado via Concurrency Limits

---

### **Casos de Uso do AWS Lambda**

1. **Processamento de Dados em Tempo Real**
    
    - Análise de logs, eventos de IoT e processamento de streaming com **Kinesis** ou **DynamoDB Streams**.
2. **Backends para APIs**
    
    - Integrado com **Amazon API Gateway**, o Lambda executa funções para responder requisições HTTP/HTTPS.
3. **Automação e Processamento em S3**
    
    - Executar funções após o upload de arquivos em buckets S3.
4. **Automatização de Tarefas e Cron Jobs**
    
    - Usar **EventBridge** (CloudWatch Events) para agendar execuções automáticas.
5. **Chatbots e Assistentes Virtuais**
    
    - Integrado com **Amazon Lex** e outros serviços de IA.
6. **Orquestração de Workflows**
    
    - Combinação com **Step Functions** para executar workflows de funções Lambda.

---

### **Vantagens**

- **Zero Administração de Infraestrutura**: Sem necessidade de gerenciar servidores.
- **Escalabilidade Automática**: Lida automaticamente com alta ou baixa demanda.
- **Custo-Efetivo**: Pague somente pelo uso real (tempo de execução e memória alocada).
- **Integração Nativa com AWS**: Funciona perfeitamente com outros serviços da AWS.
- **Alta Disponibilidade**: Regionalmente redundante por padrão.

---

### **Limitações**

1. **Tempo de Execução Limitado**: Máximo de **15 minutos** por invocação.
2. **Limitação de Estado**: Necessidade de utilizar serviços externos para armazenar dados persistentes.
3. **Cold Start**:
    - Pode haver uma latência inicial na execução da função (principalmente em ambientes não frequentes ou complexos).
4. **Tamanho do Pacote de Código**:
    - Limite de **50MB** (ZIP) ou **10GB** com contêineres.