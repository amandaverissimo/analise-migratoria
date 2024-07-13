# Dados Migratórios no Brasil: de janeiro de 2022 a junho de 2024

As informações contidas nesse Notebook descrevem o pipeline de ETL para os dados de Movimento Migratório no Brasil: registros ativos de imigrantes e movimento de entrada no país a partir de registros nos postos da Polícia Federal.

###Contexto:
Ao andar pelas ruas das grandes metrópoles brasileiras é possível identificar traços e sotaques variados, atribuidos às mais diversas nacionalidades. Percebe-se no cotidiano das cidades a presença de pessoas estrangeiras no país, seja por turismo – à passeio, pedindo informações - ou para (maior) permanência – prestando serviços e até em situação de vulnerabilidade. É possível apontar como Problema o planejamento de recursos e serviços para imigrantes no Brasil. Nesse sentido proponho confrontar os dados extraídos do Sistema de Tráfego Internacional e do Sistema de Registro Nacional Migratório para melhor percepção e análise dos movimentos migratórios no país entre janeiro de 2022 e junho de 2024. <br>
<br>

###Objetivo:
Fazer uma análise comparativa entre o tráfego internacional de pessoas e os registos ativos de imigrantes, considerando o escopo temporal das bases de dados do STI e SISMIGRA - jan/22 a jun/2024. As Perguntas que esse trabalho visa responder são:
1. Os movimentos migratórios para o Brasil têm aumentado ou diminuido?
2. Considerando UF de entrada como local de permanência: quais regiões precisam de mais recursos para lidar com a alta concentração de imigrantes registrados?
3. Quais os períodos de mais registros ativos de imigrantes?
4. A partir da nacionalidade com maior ocorrencia de migração é possível inferir a motivação desse movimento para o Brasil?
5. Qual a porcentagem de migração permanente para o Brasil em meio aos demais tipos de entrada no país?
6. Qual a proporção de emigrantes brasileiros para imigrantes estrangeiros?
<br>
<br>

###Descrição dos Dados:

Dados de domínio público extraídos da plataforma Gov.br, do Governo Federal.
Dados Abertos, inseridos no STI - Sistema de tráfego internacional e SISMIGRA - Sistema de Registro Nacional Migratório, organizados pelo DPF – departamento de Polícia Federal.<br>
<br>
Os dados do Sistema de tráfego internacional e do Sistema de Registro Nacional Migratório se apresentam em formato CSV. <br>
<br>
**Fonte**: Dados do STI: https://servicos.dpf.gov.br/dadosabertos/STI/ <br>
Dados do SISMIGRA: https://servicos.dpf.gov.br/dadosabertos/SISMIGRA/<br>
<br>

####Dados STI
Foram coletados 30 arquivos a serem explorados. Os dados estão segmentados por escopo temporal (mensal) - cada um dos documentos corresponde ao movimento migratório nas fronteiras brasileiras em determinado mês do ano – de 01/2022 a 06/2024.<br>
Cada um dos arquivos exibe os seguintes dados:<br>
UF_ATENDIMENTO: em qual unidade federativa se deu o movimento de entrada ou saída do Brasil.<br>
TIPO: Tipo de movimentação – de entrada ou saída do país. <br>
CLASSIFICACAO: Qual o objetivo do movimento (e “status” do indivíduo): de permanência, visita, ou permanencia temporária no Brasil ou ainda outras finalidades (não especificadas). <br>
NACIONALIDADE: Qual a origem do indivíduo que realizou o movimento migratório.<br>
TOTAL: Total de movimentos / indivíduos registrados pelo STI. <br>
<br>

####Dados SISMIGRA
Foram coletados 30 arquivos a serem explorados. Os dados estão segmentados por escopo temporal (mensal) - cada um dos documentos corresponde ao número de registros ativos de imigrantes em determinado mês do ano – de 01/2022 a 06/2024.
Cada um dos arquivos exibe os seguintes dados:<br>
UF: Unidade federativa em que o imigrante foi admitido<br>
NACIONALIDADE: País de nacionalidade do imigrante<br>
CLASSIFICACAO: Situação do imigrante - residente, temporário, provisório e fronteiriço<br>
QTD: Quantidade de imigrantes admitidos<br>
<br>
<br>
**Pipeline de ETL**

