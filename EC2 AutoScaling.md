## EC2 AutoScaling ##
Monitora e ajusta a capacidade automaticamente para menor custo possível
* Utilizado para conter cenários de over capacity
* Interface simples para criação de planos de escalabilidade
* Pode ser utilizado nos recursos: EC2, Frotas SPOT, ECS, DynamoDB, Aurora
* Ajuda a manter a disponibilidade do serviço ao adicionar ou remover automaticamente instâncias 
* Detecta instâncias danificadas e substitui
* Fornece também opções de escalabilidade preditiva

>Auto Scaling Group

* Conjunto de instâncias para serem tratadas como agrupamento lógico
1. Selecione o tamanho mínimo, o máximo e a capacidade desejada
2. Integração com balanceador de carga
3. Poder computacional escalável automaticamente

* Como funciona?
1. Utiliza conjunto de regras: Launch template ou Launch configuraion (que utiliza imagem AMI)
2. Sobre dentro de uma VPC e grupo de subnets

>AMI

* Utilize uma instância referência para criar uma AMI (Amazon Image) para ser utilizada no Auto Scaling

>Auto Scaling Group

* Launch Config: Selecione a imagem desejada, userdata, security group (liberando portas), par de chaves de acesso
* Grupos do Auto Scaling: Seleciono o Launch config previamente criado, seleciono as AZs e subnets relativas a elas, anexo Load Balancer (para registro automático no Target Group do Load Balancer), habilito métricas do cloudwatch para monitoramento, quantidade mínima, desejada e máxima e política de escalabilidade (com CPU utilization como métrica)

>Jumpbox

* Para acesso seguro à instâncias em uma subnet privada, é aconselhável a utilização de uma jumpbox, que nada mais é que uma instância na subnet pública acessável pela porta 22 (ssh)
* Desta forma, quando eu quiser acessar alguma instância do meu autoscaling group, defino que deve ser acessada através da jumpbox, para isso, devo copiar remotamente a chave ssh do meu autoscaling group para a minha jumpbox

