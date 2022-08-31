## AMAZON S3
>Armazenamento de objetos 
* Armazena quantidade ilimitada de dados não estruturados
Arquivos de dados são armazenados em **Bucket** (gaveta);
* Máximo de 5TB por objeto;
* Todos os objetos tem URL exclusiva e acessível globalmente (*endpoint*);
* Cada **Bucket** tem seu nome único global;
* Todos os objetos tem chave, ID, valor, metadados

>Oferece
* Durabilidade: garante que os dados não sejam perdidos, s3 standard garante 11 9's de durabilidade. Armazena de modo redundante em vários dispositivos em uma região, sempre validando integridade entre objetos;
* Disponibilidade: Acesso aos dados quando necessário, s3 standard foi criada para 99,99%. Acesso aos dados de maneira rápida;
* Escalabilidade: Capacidade ilimitada;
* Segurança: Oferece várias camadas de segurança e controle de acesso refinado;
* Performance: Compatível com vários padrões de design, muito utilizado como Backend

>Abordagens de controle de acesso no s3
1. Padrão: tudo privado
Apenas o proprietário tem acesso ao Bucket

2. Acesso público
Proprietário e outros usuários tem acesso ao bucket - case: hospedagem de site estático

3. Acesso controlado
Bucket tem controle de acesso através de políticas do IAM e do bucket, ACL's, pontos de acesso do s3, URL's pré-assinadas  --- (Adotar princípio do privilégio mínimo)

>Criptografia
1. Sem criptografia
2. Criptografia do lado do servidor: Amazon é responsável pela criptografia (gerenciado)
3. Criptografica do lado do cliente: Upload de dados criptografados

>**!!! MODELO DE CONSISTÊNCIA DE DADOS NO S3**
* Consistência de leitura: gravar e imediatamente ler
* Consistência eventual: ao substituir arquivos pode ocorrer inconsistência caso seja solicitada leitura imediata (substituição ou delete)

>Classe de armazenamento
1. S3 Standard: acesso frequente dos dados
2. S3 Standard IA: dados duradouros de baixa frequencia de acesso
3. S3 One Zone IA: dados duradouros de baixa frequencia em apenas uma zona de disponibilidade (para dados nao críticos)
4. Glacier ou Deep Archive: Dados raramente utilizados

* S3 Intelligent Tiering: movimenta automaticamente o bucket entre as classes de armazenamento de acordo com o acesso
* Ciclo de vida do S3: gerencia classes de armazenamento de acordo com opção do usuário

>Versionamento

Ao ativar versionamento, os arquivos deletados apenas são marcados como deleted e ao substituir arquivos também ficam disponíveis as versões antigas.