
Com a nuvem AWS, é possível ampliar suas atividades para novas regiões geográficas e implementar globalmente em minutos.
AWS tem infraestrutura em todo o mundo, então, ao colocar suas aplicações mais próximas aos usuários finais, você pode reduzir a latência e melhorar a experiência para o usuário.
A infraestrutura AWS é criada em torno das Regiões AWS e das Zonas de Disponibilidade (AZs).

### Regiões AWS

Uma região é um local físico do mundo onde temos vários data centers espalhados para hospedar suas aplicações.
Consistem em 3 ou mais Zonas de Disponibilidade (AZs)
Qual Região escolher? Depende de 4 fatores:
 - Compliance: Se sua aplicação, por requerimento do governo, deva ser usada somente em uma Região específica
 - Proximidade com clientes: Para se obter uma baixa latência
 - Disponibilidade de recurso AWS: Se o serviço AWS que deseja usar está disponível na Região
 - Preço


### Zonas de Disponibilidade (AZs)

Consiste de um ou mais data centers dentro de uma Região.
São localizadas bem distantes uma das outras, mas perto o suficiente para possuírem baixa latência entre AZs.
Contudo, se um desastre acontecer em uma parte da Região, estão distantes o suficiente para reduzir a chance de múltiplas AZs serem afetadas
Suponha que sua aplicação esteja rodando na Região Northern Carolina na AZ us-west-1. Se a us-west-1 falhar, você perde sua instância EC2. 
Uma melhor prática é rodar em, no mínimo, 2 AZs, rodando outra instância na us-west-1b, para se caso 1 falhar, já exista outra rodando.


### Zonas Locais

As zonas locais da AWS são um tipo de implantação de infraestrutura da AWS que coloca os serviços de computação, armazenamento, banco de dados e outros serviços seletos da AWS mais perto do público em geral, do setor e dos centros de TI, e que permitem que você entregue aplicações com requisitos de latência inferior a 10 milissegundos aos usuários.


### AWS Wavelength

Infraestrutura otimizada para aplicações móveis de computação de borda. As zonas Wavelenght são implementações de infraestrutura da AWS incorporadas nas redes 5G dos provedores de serviço de comunicação.
Isso evita latência que resultaria do tráfego de aplicações atravessasse vários saltos na internet para chegar em seu destino


### AWS Outposts

Leva serviços, infraestrutura e modelos operacionais nativos AWS para praticamente qualquer data center, seja de terceiros, grandes empresas ou espaço de co location.
Literalmente instala infraestrutura AWS no seu data center local.


### Locais de Borda

É um site usado pelo [[Amazon Cloud Front]] para armazenar em cache cópias do seu conteúdo (aplicações, sites, api) mais perto do seu cliente, para uma entrega rápida.
Suponha que suas aplicações estão no data center do Brasil, e você possui clientes na China.
Para esses clientes, você não precisa mover toda sua aplicação em uma Região na China. Ao invés dos clientes acessarem os dados no Brasil (muito lento), um cache da sua aplicação é criado e localizado na borda da localização mais próxima do seu cliente.
Assim, quando seu cliente efetuar requests, o Amazon Cloud Front recebe o cache vindo da borda e entrega ao cliente. Esse cache é mais rápido pois ele veio da borda perto da China, e não do Brasil.
Locais de borda rodam além do Cloud Front, como servidores DNS como o [[Amazon Route 53]], redirecionando os clientes para a localização correta, com latência menor.