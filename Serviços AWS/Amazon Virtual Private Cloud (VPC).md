
Permite uma camada isolada da nuvem AWS, podendo serem lançados vários recursos AWS nessa rede.
Dentro dessa rede, é possível criar várias subnets, ou seja, seções da VPC que contém recursos AWS, como instâncias EC2.
Oferece controle total da rede, como subnets públicas, privadas, endereços IP, segurança e roteamento. 

#### Tráfego de Rede em uma VPC
Quando um cliente realiza uma request, ela é enviada em forma de pacote.
Este pacote entra na VPC através do Internet Gateway, porém, antes do pacote entrar ou sair de uma subnet, suas permissões são verificadas.
As permissões indicam quem enviou e como este pacote está querendo se comunicar.
O componente da VPC que verifica as permissões para as subnets é chamado de Network Access Control List (NAC)

### Componentes de uma VPC

#### Subnets
- As **sub-redes** são divisões dentro do seu VPC. Você pode criar sub-redes públicas, que têm acesso à internet, e privadas, que são isoladas da internet.
- Cada sub-rede pode ser associada a uma **zona de disponibilidade (AZ)**, oferecendo alta disponibilidade e resiliência.
- Permite agrupar recursos pela segurança ou necessidade operacional
- Cada subnet pode se comunicar entre si, como instâncias EC2 em uma subnet pública se comunicando com o BD em uma subnet privada

#### Tabelas de Roteamento (Routing Tables)
- As **tabelas de roteamento** determinam como o tráfego é direcionado entre sub-redes, entre VPCs e para a internet. As tabelas podem ser configuradas com regras para direcionar o tráfego de entrada e saída.

#### Internet Gateway
- O **Internet Gateway** conecta o seu VPC à internet. Para que uma sub-rede pública tenha acesso à internet, ela precisa ser associada a um gateway de internet.

#### Network Access Control List (NACLs)
- **NACLs** são um segundo nível de controle de tráfego de rede. Eles atuam como firewalls na **sub-rede** e controlam o tráfego **de entrada e saída**. Ao contrário dos Security Groups, as NACLs são aplicadas de maneira **global** e afetam todas as instâncias dentro da sub-rede.
- Toda conta AWS possui uma rede default NACL, quando configurando a VPC, usar o default ou criar um personalizado.
- Performam o filtro de pacotes de um modo **stateless**, ou seja, não lembram de nada e para cada pacote que entra/sai da subnet a lista é novamente consultada


#### Security Groups
- É um firewall virtual que controla o tráfego de entrada e saída em instâncias EC2.
- Por padrão, nega todo o tráfego de entrada e saída, mas pode ser alterado
- Se múltiplas instâncias estão na mesma VPC, é possível agrupá-las em um grupo de segurança ou usar um diferente para cada uma
- O grupo de segurança é **stateful**, ou seja, diferente dos NACLs, eles lembram decisões anteriores feita pela entrada de pacotes

#### NAT Gateway
- Um **NAT Gateway** permite que instâncias em sub-redes privadas acessem a internet, mas sem permitir que a internet acesse essas instâncias. Ele é útil quando você tem instâncias privadas que precisam de acesso à internet para atualizações, mas não devem ser acessadas diretamente.

#### VPN Gateway
- O **VPN Gateway** permite a conexão segura entre sua rede on-premises e o VPC, criando uma **VPN (Virtual Private Network)**. Essa comunicação é criptografada, proporcionando segurança.

#### Peering de VPC
- O **VPC Peering** permite a comunicação entre dois VPCs. Você pode estabelecer peering entre VPCs na mesma região ou em regiões diferentes.

#### Elastic IP (EIP)
- Um **Elastic IP** é um endereço IPv4 estático que pode ser associado a uma instância EC2. É útil para garantir que o endereço IP público de uma instância seja mantido, mesmo após reiniciar a instância.



![[AclSecGroup.jpg]]