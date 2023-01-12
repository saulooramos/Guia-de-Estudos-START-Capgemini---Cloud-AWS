** AUTOMAÇÃO NA AWS **

>Processo com e sem automação

I) Processo sem automação
a) Não é compatível com repetição em escala
b) Não há controle de versões (como reverter para uma versão anterior?)
c) Falta de trilhas de auditoria (como garantir conformidade? como monitorar detalhes alterados?)
d) Gerenciamento de dados inconsistente (como garantir as configurações em várias instâncias?)
e) Precisa ser padronizado

II) Processo automatizado - IaC
a) Ferramentas para automatização e versionamento da infraestrutura
b) Gerenciamento de infraestrutura com arquivos de configuração (networking, policies, security, configurações)
c) É uma tecnologia que bate em uma API, comandos ou linguagem descritiva

III) Tecnologias IaC
a) Repositório de códigos: Github, Dockerhub, ECR
b) Tecnologias automatizáveis: Docker, aws, vmer
c) Ferramentas de IaC: Terraform, Ansible, CloudFormation
d) Entrega (CI/CD): Jenkins, Travis 

IV) Benefícios
a) Implementação mais rápida
b) Consistência das configurações
c) Limpeza simples quando desejado
d) Fácil propação de alteração nas pilhas (stacks)
e) Capacidade de reutilização
f) Repetibilidade
g) Manutenção

V) CloudFormation (Terraform aws)
a) Modelar, criar e gerenciar coleção de recursos de infraestrutura da aws
b) Coleção de recursos: Stacks ou pilhas
c) Sem nenhuma taxa extra
d) Atualiza, cria e exclui stacks
e) Permite provisionamento e atualização ordenada e previsível
f) Permite versionamento

MODELO COM RECURSOS (TEMPLATES) >> UPLOAD DO MODELO >> CRIAÇÃO DA STACK >> CRIAÇÃO DOS RECURSOS >> MANUTENÇÃO DA STACK PARA ATUALIZAÇÃO

VI) Templates do CloudFormation
a) 02 formas: Arquivos yml ou json
b) yml é mais vantajoso por ter menos detalhes
c) CloudFormation Design é um modelo com interface gráfica de drag and drop

VII) Estrutura dos modelos: Seções
a) Única seção obrigatória: resources
b) Seções podem estar em qualquer ordem, mas há uma ordem indicada
c) Format Version: versão do template
Description: Descreve o que o template faz
Metadata: Objetos que fornecem informações adicionais
Parameters: Valores a serem passados (variáveis). Ex: Instancename
Rules: Valida Parâmetros
Mapings: Mapeamento chave-valor (comum criar mapa de imagens em regiões)
Conditions: Se a variável tal = tal, condições de controle
Transform: Seção para o Lambda transformar
Resources: Recursos a serem criados. Ex: EC2 instance, subnet
Outputs: O que é esperado como retorno

VIII) Opções do CloudFormation
a) Trechos de modelo para criação de novo template
b) Exemplos de modelos aws
c) Criação de arquivo do zero

>AWS Quickstart
a) Modelos já criados pela aws para rápida utilização do cliente
b) Padrão ouro
c) Já com melhores práticas para segurança e alta disponibilidade
d) Uma arquitetura inteira com apenas alguns cliques

>AWS Systems Manager
a) Serviço para conseguir gerenciar, visualizar e controlar a infraestrutura
b) Exibir dados operacionais dos serviços, automatizar tarefas operacionais
c) Ajuda a manter a segurança e conformidade verificando os nós gerenciados e gerando relatórios ou tomando medidas corretivas sobre violações
d) Ansible, Puppet da AWS

Casos de uso
a) Agrupamento de recursos
b) Definição de forma centralizada das opções de configuração dos nós gerenciados
c) Automatização e programação de tarefas de manutenção
d) Conexão à instância sem necessidade de exposição de portas ssh 22
e) Execução de inventários automatizado
f) Observar e identificar recursos em não conformidade
g) Replicar atualização, patches de segurança, de forma centralizada

O CloudFormation atua na camada de provisionamento da infraestrutura, enquanto o SystemsManager atua no gerenciamento de configurações dentro do SO

Categorias do SSM (features)
a) Gerenciamento de operações
Gerenciamento dos recursos da aws, de incidentes, informações dos recursos através do explorer, visualização e investigação através do OpsCenter, integração com o CloudWatch para dashboards e Trusted Advisor

b) Gerenciamento de aplicações
Saúde das aplicações e integração com CloudWatch para acompanhamento, gerenciamento de grupos de recursos, configuração de aplicações através do appConfig e armazenamento hierárquico seguro através do parameterstore


c) Gerenciamento de alterações
Alteração operacional da Infraestrutura (aprovações e solicitações), automatização de tarefas de manutenção através do automation e eventos para janelas de manutenção através do calendário

d) Gerenciamento de nós
Gerenciamento da frota de instâncias, de conformidade com o compliance e de inventário com o Inventory. Gerenciamento de sessões com o session manager, execução de comandos em massa, manutenção dos nós com o state manager, patchs de segurança, instalação de agentes

e) Gerenciamento de recursos compartilhados
Documentação do SSM que define a ação (Arquivo que contém as instruções)

O SSM simplifica o gerenciamento de recursos e aplicações ao diminuir o tempo para detectção de problemas operacionais e ajuda a gerenciar a infraestrutura de modo seguro e em escala

SSM Agent
a) Agente que deve ser instalado dentro da instância para que graças a ele consigamos executar as ações (software da aws)
b) Já vem instalado em algumas imagens da aws
c) Precisa de role permissionando para execução dos comandos
