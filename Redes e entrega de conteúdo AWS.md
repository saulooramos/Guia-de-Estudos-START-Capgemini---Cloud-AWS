Redes e entrega de conteúdo AWS

Amazon VPC: Virtual Private Cloud
>Terreno reservado dentro da nuvem AWS para criação de rede virtual
>Seção isolada logicamente da nuvem AWS
>Fornece controle sobre recursos de rede virtual
*Intervalo de IP
*Criação de subnets
*Tabelas de rotas e gateways de rede
>Permite configurar rede e camadas de segurança
>Pertence a uma única região
>Ao criar VPC, é atribuido um bloco (range de Ips)

VPC PODE TER ATÉ 65536 ENDEREÇOS DE IP NO MÁXIMO (X.X.X.X/16) E 16 ENDEREÇOS DE IP NO MÍNIMO (X.X.X.X/28)

>Não é permitido alterar intervalo de endereços de IP depois de criar uma VPC
>Compatível com IPV6

Tabelas de Roteamento
>Contem um conjunto de rotas para gerenciar o tráfego de rede
>Cada rota tem uma origem e um destino
>Toda tabela de rotas tem uma rota local para comunicação dentro da VPC
>Pode ser associada a uma subnet

Subnets
>Intervalo de endereço de IP que divide uma VPC
>Pertence a uma única AZ
>Públicas (com rotas para internet) ou privadas (dados apenas saem através de NAT Gateway)
>Não podem se sobrepor

A AWS RESERVA 05 IPS DE CADA SUBNET, DEIXANDO 251 IPS DISPONÍVEIS
10.0.0.0/16 (ENDEREÇO DE REDE)
10.0.0.1/16 (COMUNICAÇÃO INTERNA) 
10.0.0.2/16 (DNS)
10.0.0.3/16 (USO FUTURO)
10.0.0.255/16 (TRANSMISSÃO DE REDE - BROADCAST)

Internet Gateway
>Associados na VPC para permitir saída para internet
>Caso exista uma rota na tabela de rotas associada a uma subnet para o internet gateway, esta subnet se torna pública
CLIENTE >>>>>> INTERNET >>>>>> IGW(VPC)

NAT Gateway
>Permite com que instâncias em uma subnet privada se conectem à internet ou outros serviços da AWS mas impede que a internet inicie conexão com essas instâncias
INTERNET >>>>>> MÁSCARA DE REDE >>>>>> INSTÂNCIA

Tabela de roteamento de subnet pública
10.0.0.0/16	local
0.0.0.0/0	igw-id

Tabela de roteamento de subnet privada
10.0.0.0/16	local
0.0.0.0/0	nat-gw-id

Como conectar a uma subnet privada?
>Virtual Private Gateway - Cria uma VPN com a VPC
>>Dependente de latência, o que pode prejudicar a aplicação

Tabela de roteamento de subnet privada com VPN
10.0.0.0/16	local
192.168.10.0/24	vgw-id

AWS Direct connect
>Conexão direta de rede privada e dedicada enrea a rede e um dos locais do DX
>Essa conexão pode reduzir custos, aumentar taxa de transferencia e conexão mais consistente (Latencia muito baixa)

Como funciona o tráfego?
Solicitação do cliente é enviada como um pacote à AWS (unidade de dados)
Entra em uma VPC por meio do igw mas antes de entrar em uma subnet verifica permissões

ACL é o componente que verifica essas permissões> Firewall virtual a nivel de subnet

A nível de instância temos o security group como firewall, que pode conter várias instancias

Grupo de segurança 						x				ACLs
Nível de instância										Nivel de subnets
Permissões atraves de regras									Regras de permissão e navegação
Stateful: tráfego de retorno é automático							Stateless: tráfego de retorno deve ser permitido
Todas as regras são avaliadas antes de permitir							Regras avaliadas em ordem numérica antes da decisão do tráfego

Entrega de conteúdo e latência de rede: desafio
(CDN) > Rede de entrega de conteúdo = rede distribuida de conteudo

>Sistema de servidores distribuido globalmente para armazenamento em Cache
>Armazenamento de copias de arquivos comumente solicitados
>Acelera entrega de conteúdo dinamico
>Melhora desempenho e escalabilidade

Serviço de CDN da AWS > Amazon CloudFront
CDN rápido, global e seguro
rede global de pontos de presença e caches regionais
modelo de autoatendimento
definição de preço com pagamento conforme uso

Pontos de presença: cache + rapido para informações mais populares
Ponto regional: cache mais lento para informações menos acessadas

Usuário >>>>> Pontos de presença >>>>> pronto regional >>>>> Servidor de Origem
CloudFront tem objetivo levar informação mais próximo ao cliente

Cobrança CloudFront
-Transferencia de dados
-Solicitações HTTPS
-Solicitações de invalidação
-IP dedicado SSL personalizado


