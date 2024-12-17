É um serviço da AWS que permite criar, gerenciar e provisionar recursos da AWS de maneira automatizada e declarativa através de **templates** (modelos) em formatos **JSON** ou **YAML**. Com o CloudFormation, você pode definir toda a infraestrutura como código, facilitando a criação e a replicação de ambientes de maneira consistente e controlada.

**Infraestrutura como Código (IaC)**:
- O **CloudFormation** permite que você defina sua infraestrutura usando código. Isso significa que você pode versionar, auditar e gerenciar sua infraestrutura da mesma maneira que gerencia seu código-fonte.

**Modelagem Declarativa**:
- Com o CloudFormation, você descreve o **que** deseja em vez de **como** fazer. O CloudFormation irá automaticamente criar e gerenciar os recursos com base na descrição fornecida no template.

**Controle de Versão**:
- Como você escreve os templates em JSON ou YAML, eles podem ser armazenados em sistemas de controle de versão (como Git), permitindo que você faça o controle e a rastreabilidade das alterações na infraestrutura.

**Rollback Automático**:
- Caso ocorra algum erro durante a criação ou atualização de recursos, o CloudFormation pode realizar um **rollback**, revertendo os recursos para o estado anterior, garantindo maior segurança e confiabilidade.