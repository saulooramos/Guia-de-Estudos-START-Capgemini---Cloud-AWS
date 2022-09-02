## ARQUITETURA COMPUTE ##
>AWS Oferece vários serviços de compute
* EC2: IaaS, baseado em instâncias e máquinas virtuais;
* Lambda: PaaS, executa funções, tem baixo custo;
* ECS,EKS, Fargate, ECR: IaaS/PaaS, baseado em containers e instâncias;
* Elastic Beanstalk: PaaS, para web apps (Infraestrutura a carfo do Elastic Beanstalk)

>Depende muito do caso de uso, arquitetura, orçamento, etc.
1. Design do app;
2. Padrões de utilização;
3. Quais definições de configurações deseja gerenciar;
4. Administração da ferramenta deve ser feita pelo time?;
5. Custo é uma variável importante?;

Uma seleção inadequada acarretará em maior custo e menor performance

>EC2

* Serviço de computação que oferece máquinas virutias (instancias) com total controle da infraestutura, região do globo, sistema operacional, capacidade;
* Escolha imagens como referencia e com apenas alguns cliques provisione servidores em minutos;
* 8 etapas para provisionamento:
1. Escolha da imagem (AMI): SO, softwares pré instalados;
Amazon Image: 
* Quick Start oferece imagens fornecidas pela AWS.
* AWS Marketplace oferece modelos pré configurados de terceiros.
* AMI's da comunidade oferece imagens compartilhadas por pessoas da comunidade.
* Benefícios: Repetibilidade, posso criar várias instâncias semelhantes utilizando mesma imagem, que pode ser criada a partir de uma instância e compartilhar entre regiões.
2. Escolha do tipo de instância: Poder computacional, CPU, memória, HD;
* Categorias: Nomenclatura - Família / geração / Recursos adicionais / tamanho
3. VPC: Onde estará provisionada? Qual subnet? Subnet publica? Privada?;
4. Role: Assume alguma permissão especial? Interage com algum outro serviço?;
5. Dados de usuário (userdata): O que deve ser executado ao iniciar (Bootstrap);
* Tem opção de subir através de arquivo ou texto com código.
6. Armazenamento: HD ou Volume de armazenamento? Qual o modelo do disco?;
* Configuração do volume raíz (onde está o SO): EBS compatível apenas com SSD
* Opção de anexar volumes adicionais e escolher tipo do disco (HDD, SSD).
* Escolher opção de criptografia.
* Armazenamento de apenas uma instância: EBS (armazenamento persistente: bancos de dados, armazenamento de arquivos, possibilidade de criação de snapshots - armazenados no s3) ou armazenamento efêmero (morre junto com a instância: Buffers, Cache, Dados transitórios) / Várias instâncias: EFS ou FSX (volume compartilhado)
* Há possbilidade de selecionar opção de instância otimizada para EBS para melhor performance do armazenamento de dados
* Tipos de volume do EBS: SSD, SSD provisionado (IOPS, inicialização e performance) / HDD, Cold HDD (taxa de transferencia, streaming, big data, data warehouse, custo menor) 
7. Firewall: Segurança, que portas estão liberadas?;
* Security Group: Firewall a nível de instância
* Porta 80: HTTP
* Porta 22: Acesso SSH;
8. Chaves SSH: Acesso;
* Elastic IP: IP Fixo associado à instância
**!!! IP ELÁSTICO NÃO ASSOCIADO TEM CUSTO**

>Tags

Tags são rótulos attachados a recursos
* Chave e valor opcionais;
* A marcação por tags é como você pode anexar metadados a uma instância no EC2;
* Facilita automação através de filtragem, alocação de custos e controle de acesso;

>Criando uma arquitetura Compute aplicável no mercado

A intenção desta arquitetura é oferecer segurança de tráfego, disponibilidade, resiliência, escalabilidade automática e carga balanceada.

1. Crio uma Amazon Image (AMI): Criamos a partir de uma instância já criada com httpd instalado. 
2. Crio instâncias em mais de uma AZ, para alta disponibilidade, ambas em uma subnet privada + NAT gateway;
3. Crio um balanceador de carga: Verifica integridade das instâncias e balanceia carga entre elas. Pode ter vários tipos de target diferentes (containers, lambda, etc.)
* 2 tipos de loadbalancers: application loadbalancer - HTTP (tráfego para app em container, suporte a solicitações HTTPS) e Network loadbalancer - TCP (tráfego TCP variável, baixa latência e milhões de solicitações);
4. Crio um target group com as instâncias privadas criadas a partir da AMI criada;
5. Aponto app loadbalancer para target group das instâncias;