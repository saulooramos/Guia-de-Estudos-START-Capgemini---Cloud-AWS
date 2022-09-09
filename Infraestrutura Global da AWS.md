## Infraestrutura Global da AWS ## 
projetada para oferecer computação em nuvem flexível, confiável, escalável, segura, entregando desempenho e alta qualidade de rede

>Região
Local físico para armazenar Zonas de Disponibilidade (AZs)
* Área geográfica
* replicação dos dados inter regiões é responsabilidade do usuário
* comunicação entre regiões é realizada pela Infraestrutura Backbone da AWS
* Cada região é interdependente e oferece redundância de conectividade
* 02 ou mais AZs
* Como escolher Região?
1. Governança de dados, requisitos legais (dados podem sair do país?)
2. Proximidade com clientes
3. Serviços disponíveis na região
4. Custos

>Zonas de Disponibilidade (AZs)
* 01 ou mais Datacenters com energia, rede e conectividade redundantes
* Capacidade de operar Apps, bancos de dados e computação com alta disponibilidade, tolerancia a falhas e escalabilidade melhor que apenas 01 datacenter
* projetadas para isolamento de falhas
* Interconectadas usando redes privadas de alta velocidade
* Você escolhe sua AZ

# BOA PRÁTICA
>AWS recomenda replicação de dados entre AZs para fins de resiliência e alta disponibilidade

* Resumo: Grupos de datacenters em uma região que oferecem elasticidade, escalabilidade, tolerância a falhas e alta disponibilidade