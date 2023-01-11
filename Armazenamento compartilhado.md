** ARMAZENAMENTO COMPARTILHADO **

V�rias inst�ncias, quando precisam utilizar o mesmo armazenamento: EFS ou FSX

>EFS
a) Sistema de arquivos para compartilhamento entre recursos da aws (inst�ncias EC2 conseguem enxergar o mesmo disco)
b) Serve para workloads e aplica��es
c) Diret�rios iniciais, testes em aplica��es, backups de bancos de dados, an�lise de dados BIGDATA, sistemas de arquivos para empresas e fluxos de trabalho de m�dia
d) Linux

>FSX for Windows
a) Sistema de arquivos para compartilhamento entre recursos no Windows server
b) NTFS
c) Namespaces DFS e replica��o
d) Compat�vel com SSD de alta performance
e) Diret�rios iniciais, lift and shift, fluxo de m�dia, an�lise de dados, desenvolvimento de software

>FSX for Lustre
a) Sistema de arquivos para Lustre
b) Alta performance