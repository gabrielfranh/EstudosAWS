Provém instâncias computacionais, que podem escalar verticalmente, ou seja, aumentar ou diminuir sua capacidade de memória ou CPU, conforme a necessidade.
As instâncias vêm de um servidor físico que pode ter mais de uma instância EC2 nele. A instância é providenciada a partir da virtualização.
No EC2, você paga somente por instâncias em execução, podendo pará-las ou encerrá-las a qualquer momento.

### Tipos de Instâncias EC2
 - #### Instâncias de Propósito Geral
	 Provém um balanceamento de CPU, memória e network.
	 Pode ser usada para diversas aplicações, como:
	 - Servidores de aplicações
	 - Servidores de jogos
	 - Servidores de backend para aplicações empresariais
	 - Pequenos e médios banco de dados

- #### Instâncias Otimizadas para Computação
	Provém um grande poder de computação/processamento para executar tarefas.
	Usada em servidores dedicados à jogos, modelagem científica.

- #### Instâncias Otimizadas para Memória
	Provém uma grande eficiência na memória que pode ser acessada pela CPU, entregando performance.
	Usada em cenários onde é necessário pré carregar uma grande quantidade de dados para iniciar aplicação, banco de dados de alta performance.

- ### Instâncias de Computação Acelerada
	Faz uso de aceleradores de hardware ou coprocessadores para performar melhor que CPUs normais.
	Usada em processamento de gráficos, cálculos de números ponto flutuantes e data pattern matching

- #### Instâncias Otimizadas para Armazenamento
	Ideal para trabalhos que necessitam de leitura e escrita a uma grande base de dados local.
	Usada em sistemas de distribuição de arquivos, aplicações de estoque, sistemas de alta frequência de transações

- #### Instâncias Otimizadas para HPC (High Performance Computing)
	Usam processadores de alta performance
	Usada em grandes simulações e deep learning


### Nomenclatura de Instâncias EC2

Exemplo: Seja o tipo de instância c5n.xlarge
 - A primeira posição (c) indica a família da instância, indica que esta pertence à família de computação acelerada
 - Segunda posição (5) indica a geração da instância
 - As demais letras antes do ponto (nesse caso somente o n) indicam atributos adicionais
 - Depois do ponto (xlarge), é indicado o tamanho da instância

### Preços no EC2

 - #### On Demand
	 Pague somente pelo que usar, podendo ser em horas ou por segundo, dependendo do tipo de instância e seu SO
	 Sem contratos ou custos mínimos e cobradas pelo tempo de uso das instâncias
	 Simples casos de uso são aplicações que possuem um padrão de uso indefinido, imprevisível

- #### EC2 Instance Savings Plan
	Contrato de 1 ou 3 anos
	O valor pago é pelo valor de hora pré-definido para um tipo de família de instância e sua Região.
	Pode resultar em um desconto de até 72% se comparado com o valor sob demanda
	É uma boa opção para flexibilidade, pois pode obter desconto rodando instâncias EC2 de uma determinada família em uma determinada Região (exemplo M5 usado em Virgínia), independente da AZ, tamanho de instância (M5 micro, large), SO ou locação.

- #### Reserved Instances
	1 ou 3 anos de contrato, com até 75% de desconto
	Pode ser pago de 3 maneiras:
	- Tudo de uma vez
	- Com entrada e parcelamento
	- Tudo parcelado
	2 tipos:
	- **Standard
		- Bom de você sabe qual tipo e tamanho você precisa e em qual Região.
		- Pré estabelecer tipo e tamanho da instância
		- Sistema Operacional
		- Locação: Padrão ou dedicada
		- Pode escolher a AZ para suas instâncias reservadas, se caso escolher, você terá a quantidade reservada para quando precisar delas
	- **Convertible
		- Para instâncias em diferentes AZs ou diferentes tipos de instâncias
		- Maior flexibilidade, pode alterar as configurações da instância (tipo, família, SO, locação e tamanho) a qualquer momento durante o contrato, ilimitado.
		- Desconto menor que o Standard

- #### Spot Instances
	Descontos de até 90% comparado com sob demanda
	Para instâncias que podem sofrer interrupções a qualquer momento
	AWS avisa 2 minutos antes de derrubar temporariamente para salvar o estado da máquina


- #### Hosts Dedicados
	Servidores físicos com capacidade EC2 dedicado ao seu uso
	De todas as opções, é a mais cara


### Escalabilidade do EC2

Escalabilidade envolve começar com os recursos necessários e mudar conforme a demanda aumenta ou diminui.
Como resultado, você paga apenas pelo recurso que usar, o que não é possível no modelo on-premises

#### EC2 Auto Scalling

Permite adicionar ou remover instâncias conforme demanda, disponibilizando somente as instâncias necessárias para atender o serviço.
Dois tipos:
- **Dinâmico:** Escala conforme a demanda
- **Previsão:** Provém instâncias baseadas em previsões de demandas para escalar mais rapidamente, pode-se usar o dinâmico em conjunto com a previsão

Dois tipos de escalonamento:
 - **Scale Up (Vertical):** Aumentar processamento
 - **Scale Out (Horizontal):** Adicionar instâncias


#### Grupos de Auto Scalling

No preparo para lançar a instância EC2, é possível definir o tamanho do grupo de Auto Scalling, você deve definir o número mínimo de instâncias EC2, ou seja, o número de instâncias que são lançadas imediatamente após criar o grupo.
Pode-se definir a capacidade desejável, mínima e máxima para escalar
Pagamento somente pelo seu uso, quando usar

![[AutoScalling.png]] 