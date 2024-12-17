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


### Preços no EC2