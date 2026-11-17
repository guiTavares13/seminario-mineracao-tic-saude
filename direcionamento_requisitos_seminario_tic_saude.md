# Documento de direcionamento e requisitos --- Seminário de Mineração de Dados

**Versão:** 1.0\
**Data:** 14/11/2026\
**Status:** proposta inicial a validar após inspeção dos microdados,
dicionário e documentação metodológica\
**Dataset candidato:** TIC Saúde 2025 --- Estabelecimentos, Cetic.br\
**Natureza:** documentação de requisitos analíticos e plano de execução
do seminário

------------------------------------------------------------------------

## 1. Contexto

O seminário será desenvolvido a partir da pesquisa TIC Saúde 2025 ---
Estabelecimentos, do Cetic.br. A proposta é investigar a maturidade
tecnológica e a capacidade de integração/troca eletrônica de informações
dos estabelecimentos de saúde brasileiros.

Esse tema também se conecta a uma linha de investigação mais ampla:
compreender as condições de infraestrutura, adoção tecnológica,
interoperabilidade e governança do ecossistema de saúde brasileiro antes
de avaliar possíveis arquiteturas para um registro eletrônico unificado
de saúde no SUS.

**Delimitação importante:** o seminário não tem como objetivo demonstrar
que blockchain é necessária, superior ou tecnicamente viável. A TIC
Saúde é uma pesquisa sobre acesso, uso e apropriação de tecnologias de
informação e comunicação nos estabelecimentos de saúde. Ela pode ajudar
a caracterizar condições e possíveis barreiras de adoção e integração,
mas não substitui testes técnicos de interoperabilidade, desempenho,
segurança, custo ou arquitetura. Blockchain deve permanecer como
motivação/contexto da pesquisa maior, não como conclusão presumida do
seminário.

## 2. Relação com o enunciado da disciplina

O trabalho deve ser um estudo focado de mineração de dados, com: - uma
pergunta-alvo clara; - justificativa da escolha e adequação do
dataset; - justificativa das decisões metodológicas; - aplicação e
avaliação de uma ou mais tarefas de mineração; - resultados que
respondam à pergunta.

Os entregáveis previstos no enunciado são: 1. apresentação em
PowerPoint; 2. notebook correspondente no Google Colab.

O enunciado não exige artigo científico nem contribuição científica
original. Métodos estabelecidos podem ser utilizados, desde que a
análise seja desenvolvida e justificada pelo estudante. O escopo deve
ser viável e as decisões devem ser defendidas.

A pergunta deve expressar o que se pretende descobrir, e não apenas
nomear uma técnica. Por exemplo, "aplicar clustering na TIC Saúde" é uma
atividade; "quais perfis de maturidade tecnológica e interoperabilidade
podem ser identificados?" é uma pergunta investigável.

## 3. Problema de pesquisa

Estabelecimentos de saúde podem diferir em disponibilidade de
infraestrutura de TIC, gestão de TI, adoção de prontuário eletrônico e
capacidade de compartilhar informações clínicas. Essas diferenças podem
estar associadas a características institucionais e territoriais.

É relevante identificar se existem perfis distintos de maturidade
tecnológica e como esses perfis se relacionam com indicadores de troca
eletrônica de informações. Isso pode ajudar a descrever heterogeneidades
e lacunas que precisam ser consideradas em iniciativas de integração
nacional de dados de saúde.

### 3.1 Pergunta principal proposta

**Quais perfis de maturidade tecnológica e interoperabilidade podem ser
identificados nos estabelecimentos de saúde brasileiros, e quais
características estão associadas a esses perfis?**

A pergunta será mantida provisoriamente. Ela deverá ser refinada após
confirmar que os microdados contêm variáveis adequadas para representar
infraestrutura, gestão de TI, prontuário eletrônico e
troca/compartilhamento de informações.

### 3.2 Perguntas secundárias

1.  Como se distribuem os recursos de infraestrutura e gestão de TI
    entre os estabelecimentos pesquisados?
2.  Qual é a distribuição da adoção de prontuário eletrônico e de
    mecanismos de troca/compartilhamento eletrônico de informações?
3.  Quais características institucionais e territoriais estão associadas
    a níveis diferentes de adoção e troca de informações?
4.  É possível identificar grupos de estabelecimentos com combinações
    semelhantes de infraestrutura, gestão de TI e interoperabilidade?
5.  Os perfis encontrados apresentam diferenças por região, localização,
    natureza administrativa ou tipo de estabelecimento, desde que esses
    recortes estejam disponíveis e sejam estatisticamente sustentáveis?
6.  Quais dimensões parecem distinguir mais os grupos: infraestrutura,
    gestão, prontuário eletrônico ou troca de informações?

As perguntas secundárias não precisam todas virar análises
independentes. Devem funcionar como decomposição da pergunta principal.
A seleção final dependerá do conteúdo do dicionário e da quantidade de
observações válidas.

## 4. Objetivos

### 4.1 Objetivo geral

Identificar e caracterizar perfis de maturidade tecnológica e
interoperabilidade dos estabelecimentos de saúde brasileiros a partir
dos microdados da TIC Saúde 2025, utilizando técnicas de análise
exploratória e mineração de dados.

### 4.2 Objetivos específicos

-   Descrever a distribuição das variáveis de infraestrutura e gestão de
    TI.
-   Caracterizar a adoção de prontuário eletrônico e a
    troca/compartilhamento eletrônico de informações.
-   Preparar e selecionar atributos adequados à análise de perfis.
-   Investigar a existência de grupos de estabelecimentos com
    características tecnológicas semelhantes.
-   Caracterizar os grupos identificados por variáveis institucionais e
    territoriais.
-   Avaliar a qualidade, estabilidade e limitações da solução de
    agrupamento.
-   Discutir o que os resultados permitem inferir sobre heterogeneidade
    tecnológica e desafios de integração.

## 5. Hipóteses de trabalho

As hipóteses abaixo são expectativas a investigar, não conclusões
antecipadas. Devem ser mantidas apenas se as variáveis disponíveis
permitirem operacionalizá-las.

  -----------------------------------------------------------------------
  ID                      Hipótese                Evidência que poderia
                                                  apoiá-la
  ----------------------- ----------------------- -----------------------
  H1                      Maior disponibilidade   Associação consistente
                          de infraestrutura de    entre indicadores de
                          TIC está associada a    infraestrutura e adoção
                          maior adoção de         de prontuário/sistemas.
                          sistemas eletrônicos de 
                          saúde.                  

  H2                      Estabelecimentos com    Diferenças nos
                          práticas ou suporte de  indicadores de troca
                          gestão de TI mais       entre categorias de
                          estruturados apresentam gestão/suporte de TI.
                          maior ocorrência de     
                          mecanismos de troca     
                          eletrônica de           
                          informações.            

  H3                      Existem perfis          Agrupamentos
                          distintos de maturidade interpretáveis, com
                          tecnológica entre os    diferenças substantivas
                          estabelecimentos de     entre os grupos e
                          saúde.                  alguma estabilidade.

  H4                      A maturidade            Diferenças entre perfis
                          tecnológica varia       ou indicadores por
                          conforme                região, localização,
                          características         esfera administrativa
                          regionais e             ou tipo de
                          institucionais.         estabelecimento.
  -----------------------------------------------------------------------

### 5.1 Cuidado na interpretação

-   Associação não significa causalidade.
-   Uma diferença entre grupos não prova que uma característica causou
    maior interoperabilidade.
-   A hipótese H3 é principalmente exploratória: clustering pode revelar
    estrutura nos dados, mas os grupos dependem das variáveis, métricas
    e parâmetros escolhidos.
-   Não se deve criar um "índice de maturidade" arbitrário e depois
    tratar o índice como verdade objetiva. Se for construído, a regra,
    os pesos e as limitações devem ser transparentes e testados.

## 6. Dataset e justificativa

### 6.1 Fonte candidata

**TIC Saúde 2025 --- Estabelecimentos, Cetic.br.**

A documentação do levantamento descreve uma pesquisa sobre acesso, uso e
apropriação de Internet e tecnologias de informação e comunicação em
estabelecimentos de saúde. A unidade de análise é o estabelecimento de
saúde.

Conforme a documentação metodológica consultada anteriormente, a
pesquisa tem abrangência nacional e população-alvo definida a partir de
estabelecimentos registrados no CNES que atendem aos critérios de
elegibilidade estabelecidos pelo levantamento. A coleta utiliza
modalidades CATI (entrevista telefônica) e questionário Web. Os
critérios exatos, período de referência, domínios de divulgação e
desenho amostral devem ser transcritos do relatório metodológico vigente
e registrados no notebook.

### 6.2 Módulos de interesse

A estrutura da pesquisa inclui módulos que, em princípio, são relevantes
para o problema:

-   **Infraestrutura e gestão de TI:** disponibilidade de recursos
    tecnológicos e aspectos da gestão de tecnologia.
-   **Prontuário eletrônico e troca de informações:** adoção de
    registros eletrônicos e mecanismos de intercâmbio/compartilhamento.
-   **Serviços ao paciente e telessaúde:** uso de tecnologias na
    prestação de serviços.
-   **Novas tecnologias:** adoção de tecnologias emergentes.
-   **Perfil do gestor:** características do respondente/gestor,
    conforme as variáveis disponíveis.

A associação entre os módulos e a pergunta de pesquisa deve ser
confirmada variável por variável no dicionário e no questionário. Não
presumir que toda variável do módulo seja adequada como atributo de
maturidade.

### 6.3 Pacote de dados a obter

  -----------------------------------------------------------------------
  Artefato                Uso no projeto          Prioridade
  ----------------------- ----------------------- -----------------------
  Microdados tratados     Base principal de       Obrigatório
  para confidencialidade  análise com Pandas      
  (CSV)                                           

  Dicionário de variáveis Descrição, códigos,     Obrigatório
  mais recente            universo, filtros e     
  (preferencialmente      categorias              
  v1.1, confirmar versão)                         

  Questionário CATI/Web   Entender redação,       Alta
                          filtros e universo das  
                          perguntas               

  Relatório metodológico  População, amostragem,  Obrigatório
                          pesos, coleta e         
                          limitações              

  Relatório de coleta     Contexto operacional da Recomendado
                          coleta e eventuais      
                          ocorrências             

  Tabelas oficiais de     Validar resultados      Alta
  resultados (XLSX/ODS)   agregados e estimativas 
                          publicadas              

  Arquivos RData/SAV e    Formatos alternativos;  Opcional
  dicionário ODS          não são necessários se  
                          CSV e XLSX forem        
                          suficientes             
  -----------------------------------------------------------------------

O CSV é a opção prática para Python, mas deve-se verificar se rótulos e
metadados presentes em formatos como SAV/RData estão descritos no
dicionário. XLSX e ODS são formatos alternativos para planilhas; não é
necessário manter ambos no fluxo analítico.

### 6.4 Adequação, cobertura e representatividade

Antes da análise, documentar:

-   população-alvo e critérios de elegibilidade;
-   unidade de observação;
-   período de referência e período de coleta;
-   método de seleção da amostra;
-   estratos, conglomerados, pesos e ajustes, se aplicáveis;
-   domínios de divulgação e recortes válidos;
-   grupos ou tipos de estabelecimentos cobertos e não cobertos;
-   limitações de confidencialidade e supressão;
-   possibilidade de dependência entre observações;
-   não resposta, dados ausentes e universos condicionais.

Não há um número mínimo universal de linhas para a atividade. A
adequação depende da relação entre a pergunta, a diversidade dos dados,
o número de observações independentes e a possibilidade de avaliar a
técnica.

### 6.5 Peso amostral e estimativas

A TIC Saúde é uma pesquisa amostral. Portanto, frequências simples dos
microdados podem não reproduzir as estimativas oficiais. É necessário
identificar os pesos e demais variáveis do desenho amostral no relatório
metodológico e no arquivo de dados.

Para estatísticas descritivas destinadas a representar a população,
avaliar o uso dos pesos e do desenho amostral. Comparar os resultados
agregados com as tabelas oficiais somente quando universo, filtros,
denominadores e categorias forem equivalentes.

Algoritmos convencionais de clustering e classificação nem sempre
incorporam diretamente desenhos amostrais complexos. Se a mineração for
feita sem ponderação, isso deve ser explicitado: os grupos descrevem a
estrutura observada na amostra analisada, e não necessariamente
estimativas populacionais diretas. Se houver ponderação ou reamostragem,
documentar precisamente como foi implementada.

## 7. Definições operacionais

Os termos precisam ser definidos com base nas variáveis observáveis:

-   **Infraestrutura de TIC:** recursos de conectividade, equipamentos,
    sistemas e outros itens efetivamente medidos no questionário.
-   **Gestão de TI:** práticas, responsabilidades, suporte, recursos
    humanos ou planejamento que o questionário efetivamente medir.
-   **Adoção de prontuário eletrônico:** presença/uso de sistema de
    registro eletrônico conforme a pergunta e o universo do
    levantamento.
-   **Troca/compartilhamento eletrônico de informações:** ocorrência de
    mecanismos ou práticas de intercâmbio que estejam explicitamente
    medidos.
-   **Interoperabilidade (proxy):** dimensão aproximada por indicadores
    de troca/compartilhamento disponíveis na pesquisa. Não afirmar
    interoperabilidade técnica plena, semântica ou conformidade com
    padrões se isso não for medido.
-   **Perfil de maturidade:** agrupamento empírico de estabelecimentos
    com combinações semelhantes de atributos selecionados. O rótulo de
    cada perfil será atribuído após interpretar as variáveis originais.

É essencial não confundir: 1. ter acesso à Internet; 2. possuir
equipamentos e sistemas; 3. utilizar prontuário eletrônico; 4. trocar
informações com outros atores; 5. realizar interoperabilidade técnica e
semântica de forma efetiva.

Essas dimensões são relacionadas, mas não equivalentes.

## 8. Plano metodológico

A estratégia recomendada é começar com análise exploratória rigorosa e
usar **clustering como tarefa central de mineração**, complementado por
associações e caracterização dos grupos. Isso se alinha à pergunta
principal sobre a existência de perfis.

### Etapa 1 --- Entendimento dos dados

1.  Carregar o CSV sem assumir previamente delimitador, codificação ou
    tipos.
2.  Inspecionar dimensões, colunas, tipos, primeiras/últimas linhas e
    valores únicos.
3.  Confrontar códigos e categorias com dicionário e questionário.
4.  Identificar unidade de análise e verificar duplicatas.
5.  Mapear variáveis de peso, estrato, conglomerado e identificadores.
6.  Identificar filtros e universos condicionais.
7.  Produzir um inventário de variáveis candidatas.

**Saída:** notebook de entendimento dos dados e tabela de inventário.

### Etapa 2 --- Qualidade e preparação

1.  Medir dados ausentes por variável e, quando pertinente, por grupo.
2.  Distinguir ausência real, não resposta, não sabe, não se aplica e
    códigos especiais.
3.  Investigar categorias raras, inconsistências e variáveis constantes.
4.  Decidir tratamento de ausentes com justificativa; não imputar
    automaticamente.
5.  Recodificar categorias somente quando houver justificativa
    conceitual.
6.  Separar variáveis nominais, ordinais, binárias e numéricas.
7.  Definir conjunto de atributos para clustering.
8.  Registrar todas as transformações para reprodutibilidade.

**Saída:** base analítica e dicionário analítico documentado.

### Etapa 3 --- Análise exploratória (EDA)

-   Frequências e proporções para variáveis categóricas.
-   Estatísticas descritivas para variáveis numéricas.
-   Distribuições, cruzamentos e visualizações.
-   Análise de ausentes e de categorias raras.
-   Comparações por região, localização, natureza administrativa e tipo,
    quando permitidas.
-   Estimativas ponderadas quando a finalidade for descrever a população
    e o desenho permitir.

**Saída:** conjunto de gráficos e tabelas que descrevem a amostra e
justificam a etapa de mineração.

### Etapa 4 --- Construção da representação analítica

O clustering depende fortemente da representação dos dados. A escolha
deve respeitar escalas e tipos:

-   Variáveis binárias: codificação coerente com as respostas e seus
    universos.
-   Nominais: codificação categórica, evitando impor ordem inexistente.
-   Ordinais: preservar a ordem quando ela for semanticamente válida.
-   Numéricas: avaliar escala e normalização conforme a métrica.
-   Dados mistos: considerar distância de Gower ou métodos próprios para
    dados categóricos/mistos.

**Alternativas técnicas:** - **K-modes:** alternativa para dados
categóricos. - **K-prototypes:** alternativa para dados mistos,
combinando componentes numéricos e categóricos. - **Distância de Gower +
clustering apropriado:** alternativa para variáveis de diferentes
tipos. - **K-means:** utilizar somente se a representação numérica, a
codificação e as premissas forem defensáveis. One-hot encoding não torna
automaticamente a distância euclidiana substantivamente adequada.

Não selecionar a técnica por familiaridade ou conveniência. Selecionar
com base na natureza dos atributos e justificar a escolha.

### Etapa 5 --- Clustering e avaliação

1.  Definir um conjunto inicial de atributos com justificativa teórica e
    empírica.
2.  Testar soluções com diferentes números de grupos/parâmetros.
3.  Comparar algoritmos ou configurações quando isso agregar evidência.
4.  Avaliar coesão/separação com métricas compatíveis com a
    representação, como silhouette e Davies--Bouldin quando aplicáveis.
5.  Examinar tamanhos dos grupos e grupos muito pequenos.
6.  Avaliar estabilidade diante de mudanças razoáveis na seleção de
    variáveis, amostra, escala ou parâmetros.
7.  Interpretar os grupos usando as variáveis originais.
8.  Dar nomes descritivos aos perfis somente depois da interpretação.

Métricas internas não provam que os grupos sejam "verdadeiros" ou
relevantes no mundo real. A interpretação substantiva e a estabilidade
são essenciais.

**Saída:** solução de agrupamento escolhida, justificativa e
caracterização dos perfis.

### Etapa 6 --- Caracterização e associação

Após obter os grupos: - comparar distribuição de infraestrutura e gestão
entre clusters; - comparar indicadores de prontuário e troca de
informações; - caracterizar os clusters por variáveis contextuais não
usadas para formar os grupos; - usar tabelas de contingência, proporções
e medidas de associação adequadas; - considerar pesos/desenho amostral e
limitações inferenciais.

É recomendável manter algumas variáveis de contexto fora do processo de
clustering e utilizá-las posteriormente para caracterizar os grupos.
Isso reduz o risco de concluir que um perfil se distingue por uma
variável que foi usada diretamente para criá-lo.

### Etapa 7 --- Análises complementares opcionais

Não são obrigatórias. Só devem ser adicionadas se a qualidade dos dados
e o tempo permitirem.

**A. Mineração de padrões frequentes** - Objetivo: encontrar combinações
recorrentes de infraestrutura, adoção de prontuário e mecanismos de
troca. - Técnicas: Apriori ou FP-Growth. - Medidas: suporte, confiança e
lift. - Cuidado: transformar variáveis em itens exige escolhas
justificadas; regras frequentes não implicam causalidade.

**B. Classificação** - Objetivo: avaliar se características disponíveis
distinguem uma categoria-alvo bem definida, por exemplo, presença de
algum mecanismo de troca, se a variável existir e tiver classes
suficientes. - Técnicas candidatas: árvore de decisão e Random Forest. -
Avaliação: divisão treino/teste ou validação cruzada; matriz de
confusão, precision, recall, F1 e métricas por classe. - Cuidado: evitar
vazamento de informação, desbalanceamento e interpretação causal. Não
usar classificação apenas para acrescentar um algoritmo.

**C. Análise espacial** - Objetivo: investigar padrões territoriais, se
a granularidade geográfica disponível for suficiente. - Técnicas
possíveis: Moran's I, hotspots e agrupamento espacial. - Cuidado:
confidencialidade pode limitar a resolução geográfica; agregados
regionais não justificam inferências em nível municipal ou de
estabelecimento. Considerar o problema da unidade de área modificável e
a incerteza amostral.

**Recomendação de escopo:** clustering + EDA + caracterização dos grupos
é o núcleo. Escolher no máximo uma análise complementar, se houver
benefício claro para responder à pergunta.

## 9. Variáveis: estratégia de seleção

A seleção final deve ocorrer somente depois de examinar o dicionário e
os microdados. Como orientação:

  --------------------------------------------------------------------------
  Dimensão                 Uso pretendido            Decisão pendente
  ------------------------ ------------------------- -----------------------
  Infraestrutura de TIC    Atributos para perfis     Identificar variáveis
                                                     disponíveis e seus
                                                     universos

  Gestão de TI             Atributos para perfis ou  Verificar conteúdo e
                           explicação                cobertura

  Prontuário eletrônico    Atributo ou variável de   Verificar se é
                           caracterização            presença, uso, tipo ou
                                                     alcance

  Troca/compartilhamento   Dimensão central de       Confirmar quais
                           interoperabilidade proxy  mecanismos são medidos

  Região/localização       Caracterização/contexto   Verificar domínios e
                                                     restrições

  Natureza                 Caracterização/contexto   Verificar categorias e
  administrativa/tipo de                             tamanho amostral
  estabelecimento                                    

  Pesos e desenho amostral Estimação e interpretação Localizar no
                                                     dicionário/relatório
  --------------------------------------------------------------------------

### 9.1 Separação entre atributos e variáveis de caracterização

Definir previamente: - **Atributos de agrupamento:** variáveis que
determinam a formação dos clusters. - **Variáveis de caracterização:**
variáveis utilizadas depois para interpretar diferenças entre
clusters. - **Variáveis de desenho:** pesos, estratos, conglomerados e
identificadores. - **Variáveis excluídas:** identificadores, variáveis
sem variação, variáveis com universo incompatível ou dados que não
respondam à pergunta.

Evitar incluir no clustering variáveis que sejam apenas identificadores
ou que reproduzam diretamente o rótulo que será usado para validar a
interpretação.

## 10. Requisitos de qualidade e rigor científico

O trabalho deverá atender aos seguintes requisitos:

**RQ-01 --- Rastreabilidade:** toda fonte, arquivo, versão e data de
download devem ser registrados.

**RQ-02 --- Adequação da pergunta:** a pergunta deve ser respondível com
as variáveis e a unidade de análise disponíveis.

**RQ-03 --- Adequação do dataset:** documentar origem, processo de
coleta, população, unidade, período, cobertura, omissões, viés de
seleção e dependência entre observações.

**RQ-04 --- Qualidade dos dados:** documentar ausentes, códigos
especiais, categorias raras, inconsistências e decisões de tratamento.

**RQ-05 --- Desenho amostral:** localizar e considerar pesos e variáveis
do plano amostral; explicitar limitações se a técnica não os incorporar.

**RQ-06 --- Justificativa metodológica:** explicar por que cada técnica,
métrica, representação e parâmetro foi escolhido.

**RQ-07 --- Reprodutibilidade:** notebook deve executar do início ao
fim, com transformações explícitas e resultados reproduzíveis sempre que
possível.

**RQ-08 --- Avaliação:** avaliar qualidade e estabilidade dos
agrupamentos; não se limitar a apresentar um gráfico de clusters.

**RQ-09 --- Interpretação:** traduzir resultados técnicos em perfis
compreensíveis, com evidências nas variáveis originais.

**RQ-10 --- Limites de inferência:** distinguir descrição, associação e
causalidade; não generalizar além da população/domínios sustentados pelo
desenho.

**RQ-11 --- Transparência:** reportar resultados que não confirmem
hipóteses e decisões que alteraram o escopo.

**RQ-12 --- Coerência dos entregáveis:** notebook e apresentação devem
apresentar os mesmos números, definições e conclusões.

## 11. Riscos e estratégias de mitigação

  -------------------------------------------------------------------------
  Risco                   Consequência            Mitigação
  ----------------------- ----------------------- -------------------------
  Variáveis não           Conclusões exageradas   Usar "proxy de
  representam                                     troca/compartilhamento" e
  interoperabilidade                              delimitar o conceito
  técnica                                         

  Universos condicionais  Comparações incorretas  Ler questionário e
  diferentes                                      filtros; documentar
                                                  denominadores

  Dados ausentes ou       Instabilidade e perda   Diagnosticar antes;
  categorias raras        de observações          simplificar escopo quando
                                                  necessário

  Desenho amostral        Estimativas             Identificar
  ignorado                potencialmente          pesos/desenho; separar
                          enviesadas              descrição da amostra e
                                                  inferência populacional

  Dados mistos tratados   Distâncias sem          Usar métodos/métricas
  como puramente          significado             compatíveis
  numéricos                                       

  Clusters instáveis      Perfis pouco confiáveis Sensibilidade a
                                                  variáveis, parâmetros e
                                                  amostras

  Excesso de técnicas     Análise superficial e   Manter clustering como
                          prazo comprometido      núcleo e limitar
                                                  complementos

  Confundir associação    Afirmações indevidas    Linguagem associativa e
  com causalidade                                 limitações explícitas

  Confundir seminário com Escopo excessivo        Manter blockchain como
  tese                                            contexto da linha futura,
                                                  não como objeto de
                                                  validação neste estudo
  -------------------------------------------------------------------------

## 12. Estrutura de execução e notebooks

Sugestão de organização:

``` text
seminario-tic-saude/
├── README.md
├── docs/
│   ├── direcionamento_pesquisa.md
│   ├── dicionario_analitico.md
│   └── decisoes_metodologicas.md
├── data/
│   ├── raw/
│   │   └── original/
│   ├── reference/
│   └── processed/
├── notebooks/
│   ├── 01_entendimento_dos_dados.ipynb
│   ├── 02_preparacao_e_eda.ipynb
│   ├── 03_mineracao_perfis.ipynb
│   └── 04_validacao_e_resultados.ipynb
└── outputs/
    ├── figures/
    └── tables/
```

### Notebook 01 --- Entendimento dos dados

-   carregar e inspecionar os arquivos;
-   validar estrutura, unidade e dicionário;
-   identificar pesos, desenho, filtros e universos;
-   construir inventário de variáveis.

### Notebook 02 --- Preparação e EDA

-   qualidade e ausentes;
-   recodificações;
-   estatísticas e visualizações;
-   análise descritiva ponderada quando aplicável;
-   definição da base analítica.

### Notebook 03 --- Mineração de perfis

-   seleção e representação dos atributos;
-   comparação de algoritmos/parâmetros;
-   avaliação interna e estabilidade;
-   escolha e interpretação dos clusters.

### Notebook 04 --- Validação e resultados

-   caracterização dos grupos;
-   cruzamentos e associações;
-   análise de sensibilidade;
-   consolidação de gráficos, tabelas e respostas às perguntas.

Os notebooks podem ser consolidados em um único Colab se isso for mais
simples para a entrega, desde que as seções sejam organizadas e a
execução seja reproduzível.

## 13. Plano de apresentação

Estrutura sugerida para os slides:

1.  Título e contexto.
2.  Problema e relevância.
3.  Pergunta principal e perguntas secundárias.
4.  Hipóteses.
5.  Dataset: fonte, população, unidade e período.
6.  Cobertura, amostragem e limitações.
7.  Variáveis selecionadas e definição operacional dos conceitos.
8.  Preparação e análise exploratória.
9.  Técnica de mineração e justificativa.
10. Avaliação/seleção da solução.
11. Perfis identificados e suas características.
12. Associações e diferenças entre grupos.
13. Respostas às perguntas e discussão das hipóteses.
14. Limitações e ameaças à validade.
15. Conclusão e próximos passos.

A quantidade de slides deve ser adaptada ao tempo definido pelo
professor.

## 14. Critérios de aceite do estudo

O estudo pode ser considerado pronto quando:

-   [ ] a pergunta principal é clara e respondível pelo dataset;
-   [ ] a população, unidade, período, cobertura e desenho amostral
    foram descritos;
-   [ ] as variáveis usadas têm significado e universo confirmados;
-   [ ] as decisões de preparação estão documentadas;
-   [ ] a técnica de mineração é adequada ao tipo de dado;
-   [ ] os resultados foram avaliados e interpretados;
-   [ ] cada pergunta recebe uma resposta sustentada por evidência;
-   [ ] hipóteses são discutidas sem forçar confirmação;
-   [ ] limitações e ameaças à validade são explícitas;
-   [ ] notebook e slides são consistentes e reproduzíveis.

## 15. Conexão com a pesquisa de longo prazo

Os resultados poderão servir como diagnóstico empírico inicial sobre a
heterogeneidade tecnológica dos estabelecimentos de saúde. A partir
deles, uma pesquisa posterior poderá aprofundar questões que a TIC Saúde
não resolve diretamente:

-   quais padrões técnicos de interoperabilidade são utilizados;
-   em que medida os sistemas implementam padrões como HL7 FHIR;
-   como ocorre a integração com a Rede Nacional de Dados em Saúde
    (RNDS);
-   quais problemas de governança, identidade, consentimento, segurança
    e qualidade de dados persistem;
-   quais requisitos de infraestrutura, disponibilidade, latência,
    escalabilidade e operação existem;
-   se há um problema real que justifique tecnologia de registro
    distribuído;
-   quais alternativas arquiteturais centralizadas, federadas ou
    híbridas atendem aos requisitos;
-   se blockchain agrega valor em auditoria, integridade,
    rastreabilidade ou governança, considerando custos, privacidade e
    complexidade.

Uma hipótese arquitetural futura a investigar --- não uma decisão de
projeto --- seria manter dados clínicos fora da cadeia e avaliar o uso
de registros verificáveis, hashes ou eventos de auditoria em uma camada
distribuída. Essa possibilidade exigiria estudo próprio de privacidade,
LGPD, governança, desempenho, segurança, interoperabilidade e comparação
com alternativas convencionais.

**Conclusão de escopo:** o seminário deve responder a uma pergunta
empírica sobre perfis e condições de maturidade
tecnológica/interoperabilidade. Ele pode fundamentar a motivação da
pesquisa maior, mas não deve tentar resolver antecipadamente a
arquitetura do prontuário unificado ou validar blockchain.
