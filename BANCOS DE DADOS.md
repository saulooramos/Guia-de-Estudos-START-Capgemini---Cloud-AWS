## BANCOS DE DADOS ##

Divididos em 2 categorias:
1. Gerenciados pela AWS
2. Não gerenciados pela AWS
* Desafios gerenciais: Manutenção do servidor, consumo, softwares, backups, segurança, instalação de patches, SO, escalabilidade

>Tipos de Bancos de Dados
1. Relacionais : SQL, Oracle DB, MySQL, Postgres
* Linhas e colunas; Banco de dados fixo; usa SQL; Vertical; Esquema de consulta
* Focado na facilidade do uso, integridade dos dados, redução no armazenamento em linguagem comum
* Precisa de regras rígidas (conformidade); Cumprimento de padrões de qualidade dos dados; Não precisa de capacidade de performance de leitura e gravação


2. Não relacionais : MongoDB, Cassandra, DynamoDB, Redis, Mimecast
* Chave-valor; Dinâmico; Focado na coleta de documentos; Horizontal
* Focado em flexibilidade, escalabilidade, alta performance com API's altamente funcionais
* Dimensionamento de BD horizontal com grande volume de dados. Dados não se adaptam bem aos esquemas tradicionais; Taxas de leitura e gravação altas

>RDS
Serviço gerencial de BD relacional de alta performance, disponibilidade e compatibilidade

* Foco nos dados e otimização da aplicação (Infraestrutura gerenciada pela AWS)
* Master (instância principal do RDS) tem classes disponíveis para seleção com diferences CPU, memória e desempenho além de opções de armazenamento em SSD, magnético ou IOPS provisionado
* Via RDS os flavors compatíveis: MySQL, Aurora, SQL Server, PostgreSQL, MariaDB
* RDS multi AZ - Estrutura de múltiplas zonas de disponibilidade (cria um Slave em uma outra zona para disponibilidade)
* RDS réplicas de leitura - Cria réplicas do BD para leitura, visando evitar sobrecarga no master (evitando concorrência de leitura e gravação)
* Amazon Aurora: Compatível com PostgreSQL e MySQL. utilizado para processamento transacional online (OCTP); até 5x taxa de transferencia do MySQL e até 3x taxa de transferência do PostgreSQL; Réplica de até 6 maneiras em 3 AZs e requer pouca alteração na aplicação.

>Redshift
Serviço de Data Warehousing da AWS

* Processamento e análise de dados online (OLAP)
* Armazena conjunto de dados muito grande, altamente estruturados e acessados com frequência
* Integração com S3 para armazenamento de Hexabytes de dados estruturados ou não

>DynamoDB
Seviço não relacional de BD da AWS

* Para performance e alta escalabilidade serveless
* Programação orientada a eventos
* Criptografia e controle de acessos e Backups
* Dados simples e de alto volume
* Dimensionado para escalar rapidamente
* Maior taxa de transferencia e menor latência
* Utiliza tabelas NoSQL
* Itens podem ter atributos diferentes
* Armazenamento em cache de memória
* Suporte a mais de 20 milhões de solicitações/seg
