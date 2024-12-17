Funciona como um único ponto de entrada do tráfego da Web para o grupo de Auto Scale.
Conforme é adicionada ou removida instâncias para responder a demanda de tráfego, essas requisições são encaminhadas para o load balancer primeiro. Depois, são encaminhadas entre as instâncias para não haver gargalos.
O Elastic Load Balancer distribui o tráfego para aplicações de mesma ou diferentes AZs, porém não distribui para Regiões diferentes.
O EC2 Auto Scale e o ELB são serviços diferentes porém trabalham em conjunto.

### Tipos de Load Balancer

- #### Application Load Balancer (ALB)
	Funciona na camada 7 (Aplicação) no modelo OSI
	Suporta HTTP e HTTPS (entende os headers, cookies, e conteúdo do tráfego)
	Oferece roteamento baseado em Regras, incluindo:
	 - Roteamento por path (ex: **/api** para um caminho, **/blog** para outro)
	 - Roteamento por host (ex: **app.example.com** e **api.example.com**)
	 - Roteamento por parâmetros no **header** ou **query string**
	Permite health check nos destinos
	Suporta WebSockets e HTTP/2
	Pode ser usado para **balancear contêiners** no ECS/EKS através de porta dinâmica
	O ALB distribui as requisições recebidas para os **targets** (destinos) registrados em **target groups**.
	Os **targets** podem ser:
    - Instâncias **EC2** (ex.: uma aplicação hospedada em várias instâncias).
    - **Containers** (como ECS/EKS, suportando portas dinâmicas).
    - Endereços **IP privados** (em redes dentro de VPCs).
    - **Lambda functions** (para chamadas serverless).
	Ele utiliza um algoritmo de **Round Robin** por padrão para distribuir as requisições.
	Casos de uso:
	 - Aplicações **Web** tradicionais e modernas.
	- **APIs RESTful** e microsserviços.
	- Aplicações baseadas em **containers** com ECS, EKS ou Fargate.
	- Roteamento detalhado com base em **URLs** ou **hostnames**.

![[ALB.png]]

- #### Network Load Balancer (NLB)
	Opera na **camada 4** (Transporte) do modelo OSI.
	Funciona com **TCP**, **UDP** e **TLS**.
	Pode lidar com milhões de requisições por segundo, com **latência extremamente baixa**.
	Usa **IP estático** para o balanceador ou **Elastic IP** (EIP).
	Suporta **TLS Offloading** (descriptografia de TLS no load balancer).
	Muito eficiente para **tráfego pesado** e cenários de baixa latência.
	Casos de Uso:
	- Aplicações que exigem **baixa latência** e alto desempenho, como:
    - Serviços **de jogos** online.
    - Aplicações financeiras e transacionais.
    - **VoIP** ou outras aplicações em tempo real.
- Balanceamento de cargas em **TCP** ou **UDP**.
- Sistemas que precisam de **IPs fixos** no load balancer.


- #### Gateway Load Balancer (GLB)
	Projetado para **tráfego de rede**, opera como um **gateway** na camada 3.
	Facilita o uso de **appliances de rede de terceiros** em sua arquitetura, como firewalls, sistemas de inspeção ou IDS/IPS.
	Combina **balanceamento de carga** com a **transparência do tráfego**.
	Mantém o tráfego **bidirecional**, garantindo que pacotes de ida e volta passem pelo mesmo appliance.
	Casos de Uso:
	- Balanceamento de carga em **firewalls virtuais**.
	- Integração de **appliances de segurança** de parceiros (ex: Palo Alto, Fortinet, CheckPoint).
	- **Inspeção de tráfego** em redes VPC.


![[LoadBalancerDifferences.png]]