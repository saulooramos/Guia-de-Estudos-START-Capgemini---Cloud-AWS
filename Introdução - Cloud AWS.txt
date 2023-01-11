Computação em Nuvem
-Alta disponibilidade
-Resiliencia
-Automação
-IaC
-DevOps
-Versionamento

>É a entrega sob demanda de poder computacional: Bancos de dados, Armazenamento, Aplicativos

TI Tradicional						x					Computação em Nuvem
Hardware											Software
Exige espaço, equipe, segurança física, planejamento e capital					flexível, escalável e resiliente
Ciclo longo e muitas vezes demorado de aquisição de hardware					Mudança rápida, facilidade e economia
Exige previsão e provisionamento a partir dos picos de demanda					API's > Automatização de tarefas

Pagamento, escalabilidade sob demanda
Ganho em agilidade

IaaS: Infraestrutura como serviço: gerenciamento alto sobre os recursos de TI
- Ganho em flexibilidade e autonomia: cliente é responsável por gerenciar acessos, segurança, aplicação de patches
EC2 ; EBS ; VPC 

PaaS: Plataforma como serviço: menor gerenciamento sobre os recursos de TI
- Infraestrutura gerenciada pela AWS (Patches de SO, de bancos de dados, configurações de firewall e recuperação): cliente foca apenas em códigos e dados
Lambda ; RDS ; Elastic Beanstalk

SaaS: Software como serviço: nenhum gerenciamento sobre os recursos de TI
- Menor flexibilidade, pagamento conforme utilização (normalmente acessados no navegador, app móvel ou API): cliente foca apenas em utilizar o software e fornecer dados
Trusted Advisor ; Shield ; Chime

Implantação
Cloud First: subir na cloud por padrão

Modelo de responsabilidade
Cliente - segurança na nuvem
1)Plataforma, apps, gerenciamento de Id de acesso
2)Configuração de SO, rede e firewall
3)Criptografia no lado do cliente, autenticação e integridade dos dados
4)Criptografia no lado do servidor (sistema de arquivos de dados)
5)Proteção do tráfego de rede (criptografia, integridade, IPs)

AWS - segurança da nuvem
1)Software
2)Computação
3)Armazenamento
4)Bancos de dados
5)Rede
6)Infraestrutura global de hardware
7)Regiões
8)Zonas de Disponibilidade
9)Ponto de presença