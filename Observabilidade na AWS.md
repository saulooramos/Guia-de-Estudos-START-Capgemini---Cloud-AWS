** OBSERVABILIDADE NA AWS **

> CloudTrail
a) Acompanhamento de atividades para rastreabilidade, dedo duro da aws
b) Registra em trilhas todas as chamas de API, fornecendo histórico de eventos dos últimos 90 dias sem custo adicional
c) Útil para fazer uma análise de segurança, descobrir o que, quando e por quem algo foi bloqueado
d) Categorias do CloudTrail
Events: Registro de atividade pode ser categorizado como management event, data event e insight event
Event History: Histórico de eventos para visualização disponível gratuitamento dos últimos 90 dias
Trail: Trilha do CloudTrail para análise e entrega no S3 ou CloudWatch logs/events, podendo extender o tempo para mais de 90 dias
Management Events: Eventos de gerenciamento, operações realizadas nos recursos da conta
Data Events: Eventos de dados, objetos no S3, tabelas no Dynamo
Insight Events: Ajuda na identificação de atividades incomuns, anomalias. Para melhor segurança

O CloudTrail é um serviço de rastreabilidade, com opção de filtragem para listar e visualizar o que foi criado/modificado

> CloudWatch
a) Garantia de consistencia e monitoramento com alertas para os recursos da aws
b) Serviço para Engenheiros DevOps, desenvolvedores, SRE e gerentes de TI
c) Utiliza métricas para acompanhamento que podem ser mantidas por até 15 meses
Mais de 400 métricas disponíveis com filtros de pesquisa customizadas, formas de visualização
d) Opções variadas para monitoramento, billing, cpu utilization. Configuração de alertas ao atingir cota estipulada (SNS, reboot, trigger para lambda, incidente no SSM)
e) Métrica de detecção de anomalias em instâncias EC2 disponível para habilitação
f) Alarmes compostos são alarmes com 2 ou mais alarmes (leva em conta estado de outros alarmes)
g) Estados:Ok, insuficient data ou alarm
h) LogGroups: Armazena logs do CloudTrail e route 53 para centralização dos logs. Serviço escalável, permite consulta de logs ordenados por tempo
i) LogInsights: Insights de logs
j) Dashboard: Painél gráfico para visualização de parâmetros e métricas. Possibilidade de criação de painéis com métricas e formatos selecionados

> Trusted Advisor
a) Inspeciona o ambiente e faz recomendações de economia, performance, segurança
b) Tem limitações dependendo do nível de suporte
c) Escaneia a infraestrutura e compara com boas práticas aws
d) Categorias:
Otimização de custo
Performance
Segurança
Tolerancia a Falhas
Limites de Serviço