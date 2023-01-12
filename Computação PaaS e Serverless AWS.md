** COMPUTAÇÃO PAAS E SERVERLESS AWS ** 

> Elastic Beanstalk
a) Maneira mais fácil de colocar uma aplicação web em execução
b) Serviço gerenciado, provisionamento e configuração da infraestrutura, implantação, balanceamento de carga, escalabilidade automatica, monitoramento de integridade, análise e depuração e registro em log por conta da aws
c) Não há custo adicional, pagamento somente pelos recursos do Elastic Beanstalk
d) Preocupe-se somente com o código da sua aplicação
e) Tipos de implantação: http, servidor para aplicações, intérprete de linguagem, Sistema Operacional, Host
f) Linguagens: Java, .Net, php, node.js, Python, Ruby, Go, Docker
g) Opção de upload do conteúdo
e) Servidores: apache, nginx, IIs, Puma, passenger

> Noções básicas de Containers
a) Método de virtualização do Sistema Operacional
b) Benefícios: Repetível, ambiente de execução autônomo, software é executado da mesma forma em diferentes ambientes, lançamento e interrupção mais rápido, consistência dos ambientes, portabilidade
c) Containers compartilham do Sistema Operacional da instância, enquanto VM's precisam cada uma de seu próprio SO
d) Docker
Plataforma que permite criar, testar e implementar aplicações containerizadas
Executa container a partir de imagens (Docker file)
Uma aplicação containerizada deve conter tudo o que é necessário para sua execução (bibliotecas, ferramentas)
O Docker é instalado em cada servidor e oferece comandos simples para criação, inicio e encerramento de containers
Benefícios: Padronização de ambientes, redução de conflitos entre pilhas de linguagens e versões, containers como serviço, execução de microsserviços com implantação padronizada, portabilidade para processamento de dados

> ECS
a) Gerenciamento de containers rápido e escalável
b) Orquestra a execução de containers do Docker
c) Mantém e escala frota de nós que executam containers
d) Remove complexidade da criação de infraestrutura
e) Integrado aos recursos do EC2: Load Balancing, Security Groups, Elastic Block Storage, IAM
f) Atua na distribuição das chamadas de containers

Opçõs de Cluster do ECS
a) Cluster baseado no EC2
Gerenciamento dos mecanismos do Docker, Sistemas operacionais

b) Cluster baseado no Fargate (Serverless)
Gerenciamento apenas das aplicações, bins/libs. Não gerencia instâncias, apenas containers

A AWS recomenda começar pelo Fargate, menos flexível e menos autonomia

> ECR
a) Armazenamento de imagens de containers
b) Funciona como o DockerHub
c) Integrado ao ECS
d) Suporte a imagens Docker
e) Colaboração em equipe
f) Controle de acesso

> Lambda
a) Faça upload do seu código e execute uma função lambda, executada somente quando acionada
b) Pague somente pelo tempo de execução da função
c) Arquitetura orientada a eventos
d) Benefícios: Oferece suporte à várias linguagens (Java, Go, PowerShell, Node.js, C#, Python, Ruby), administração totalmente automatizada, tolerância à falhas integradas, suporte à orquestração de várias funções, pay-as-you-go
e) Limites do Lambda: até 1000 execuções por região, 75 Gb de armazenamento de camadas por função, alocação máxima de memória de 3.008 ms, tempo limite de execução: 15 minutos, entre outras
