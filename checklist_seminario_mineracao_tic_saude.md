# Checklist --- Seminário de Mineração de Dados

> Projeto: maturidade tecnológica e interoperabilidade dos
> estabelecimentos de saúde brasileiros\
> Fonte principal prevista: TIC Saúde 2025 --- Estabelecimentos
> (Cetic.br)\
> Status inicial: planejamento; validar os arquivos e o desenho amostral
> antes de fechar as perguntas e técnicas.

## 1. Preparação e rastreabilidade

-   [x] Guardar o ZIP original sem modificações em `data/raw/original/`. -> Esta na raiz do projeto
-   [x] Registrar URL de origem, data de download, nome do arquivo,
    versão e data de publicação. -> https://www.cetic.br/pt/arquivos/saude/2025/estabelecimentos/?utm_source=chatgpt.com, 15/11/26,, versão 1.0, 2026-05-12
-   [ ] Extrair os arquivos mantendo a estrutura original.
-   [x] Identificar qual arquivo contém os microdados e confirmar -> tic_saude_2025_estabelecimentos_pós_cec_base_de_microdados\1. Base de microdados\tic_saude_2025_estabelecimentos_pós_cec_base_de_microdados_v1.0.csv
    extensão, delimitador, codificação e separador decimal.
-   [ ] Identificar a versão mais recente do dicionário de variáveis;
    conferir se é a v1.1.
-   [ ] Obter o questionário aplicado (CATI e/ou Web) para entender o
    significado e o universo de cada pergunta.
-   [ ] Obter o relatório metodológico e o relatório de coleta.
-   [ ] Baixar as tabelas oficiais de resultados (XLSX/ODS) para
    validação de estimativas agregadas.
-   [ ] Registrar restrições de uso, confidencialidade e regras de
    divulgação dos microdados.
-   [ ] Criar um `README.md` com a estrutura dos arquivos e as decisões
    tomadas.

## 2. Entendimento do levantamento e do dataset

-   [ ] Confirmar a população-alvo e os critérios de inclusão dos
    estabelecimentos.
-   [ ] Confirmar a unidade de análise/observação: estabelecimento de
    saúde.
-   [ ] Registrar período de referência e período de coleta.
-   [ ] Entender o plano amostral, estratos, conglomerados, pesos e
    eventuais ajustes de não resposta.
-   [ ] Identificar domínios para os quais o levantamento permite
    divulgação (Brasil, regiões, localização e demais recortes
    documentados).
-   [ ] Identificar variáveis de identificação, estratificação,
    ponderação e controle estatístico.
-   [ ] Mapear os módulos do questionário relevantes:
    infraestrutura/gestão de TI; prontuário eletrônico/troca de
    informações; serviços ao paciente/tele saúde; novas tecnologias;
    perfil do gestor.
-   [ ] Verificar se cada variável é aplicável a todos os
    estabelecimentos ou apenas a um universo filtrado.
-   [ ] Distinguir "não", "não sabe", "não respondeu", "não se aplica" e
    valores suprimidos/recodificados.
-   [ ] Verificar se existem variáveis derivadas e como foram
    construídas.
-   [ ] Conferir se os dados anonimizados ou tratados por
    confidencialidade afetam análises geográficas ou identificadores.

## 3. Inspeção inicial com Python/Pandas

-   [ ] Carregar o arquivo sem assumir previamente `sep`, `encoding` ou
    tipos.
-   [ ] Inspecionar dimensões, nomes de colunas, tipos, amostras de
    linhas e valores únicos.
-   [ ] Conferir duplicatas e a unicidade da unidade de análise.
-   [ ] Calcular proporção de ausentes por variável e por grupo
    relevante.
-   [ ] Identificar códigos especiais, categorias raras e
    inconsistências.
-   [ ] Cruzar nomes/códigos com o dicionário e questionário.
-   [ ] Produzir tabela de qualidade: variável, descrição, tipo,
    universo, ausentes, categorias e decisão.
-   [ ] Não excluir registros ou imputar valores sem documentar
    justificativa.
-   [ ] Verificar se os pesos e variáveis do desenho amostral estão
    disponíveis e interpretáveis.

## 4. Delimitação da pergunta de pesquisa

-   [ ] Definir uma pergunta principal que os dados realmente consigam
    responder.
-   [ ] Definir 2--4 perguntas secundárias diretamente relacionadas.
-   [ ] Definir população, unidade de análise, variáveis de resultado e
    fatores explicativos.
-   [ ] Definir o que será considerado "maturidade tecnológica" e
    "interoperabilidade".
-   [ ] Não tratar acesso à Internet, existência de prontuário
    eletrônico e troca de dados como conceitos equivalentes.
-   [ ] Definir evidências que apoiariam ou enfraqueceriam cada
    hipótese.
-   [ ] Escrever limites explícitos: estudo observacional, transversal
    (conforme o recorte), associações e não causalidade.
-   [ ] Confirmar que o escopo cabe no tempo e nos entregáveis do
    seminário.

## 5. Construção dos atributos analíticos

-   [ ] Selecionar variáveis de infraestrutura e gestão de TI.
-   [ ] Selecionar variáveis de prontuário eletrônico e
    compartilhamento/troca de informações.
-   [ ] Selecionar variáveis de contexto: região, localização, natureza
    administrativa e tipo de estabelecimento, quando disponíveis.
-   [ ] Separar atributos usados para construir perfis daqueles usados
    para caracterizá-los.
-   [ ] Criar indicadores compostos somente se houver justificativa
    conceitual e regra transparente.
-   [ ] Documentar recodificações, agrupamentos e tratamento de
    categorias raras.
-   [ ] Evitar vazamento de informação: não usar como preditores
    variáveis que definem diretamente o resultado que se pretende
    prever.
-   [ ] Avaliar se os indicadores compostos dão pesos arbitrários a
    dimensões diferentes.
-   [ ] Considerar análise de sensibilidade para escolhas de codificação
    e seleção de variáveis.

## 6. Análise exploratória e preparação

-   [ ] Descrever a amostra e, quando apropriado, apresentar estimativas
    ponderadas.
-   [ ] Examinar distribuições, frequências e cruzamentos.
-   [ ] Visualizar ausentes e padrões de não resposta.
-   [ ] Verificar categorias desbalanceadas e eventos raros.
-   [ ] Tratar variáveis nominais e ordinais de acordo com sua escala.
-   [ ] Normalizar/escalar apenas quando a técnica exigir ou se
    beneficiar disso.
-   [ ] Justificar distância/métrica para dados mistos; não aplicar
    distância euclidiana indiscriminadamente a categorias nominais.
-   [ ] Comparar resultados ponderados e não ponderados quando o desenho
    amostral exigir essa cautela.
-   [ ] Validar estimativas agregadas com as tabelas oficiais,
    respeitando universo, filtros e margem de erro.

## 7. Mineração de dados --- plano principal sugerido

-   [ ] **Clustering exploratório:** testar perfis de maturidade
    tecnológica/interoperabilidade.
-   [ ] Preparar um conjunto de atributos conceitualmente coerente para
    agrupamento.
-   [ ] Comparar algoritmos adequados a dados mistos (por exemplo,
    k-modes/k-prototypes ou distância de Gower com agrupamento
    apropriado); usar k-means apenas se a representação numérica e as
    premissas forem defensáveis.
-   [ ] Avaliar diferentes números de grupos e estabilidade dos perfis.
-   [ ] Usar métricas internas com cautela: silhouette, Davies--Bouldin
    e/ou outras compatíveis com a representação escolhida.
-   [ ] Interpretar cada grupo pelas variáveis originais, não apenas
    pelo rótulo do cluster.
-   [ ] Caracterizar os grupos por região, localização, natureza
    administrativa e tipo de estabelecimento.
-   [ ] Se o tempo permitir, comparar com uma segunda abordagem de
    agrupamento ou análise de sensibilidade.

## 8. Análises complementares (selecionar conforme dados e tempo)

-   [ ] **Associação/padrões frequentes:** investigar combinações de
    infraestrutura, prontuário e troca de dados; usar suporte, confiança
    e lift, com limiares justificados.
-   [ ] **Classificação exploratória:** somente se houver um alvo claro
    e classes com quantidade suficiente; usar árvore de decisão ou
    Random Forest como modelos interpretáveis/comparativos.
-   [ ] **Análise espacial:** somente se a geografia disponível tiver
    resolução e qualidade adequadas; considerar distribuição regional e,
    se houver unidades espaciais suficientes, Moran's I/hotspots.
-   [ ] Evitar incluir técnicas apenas para demonstrar variedade; cada
    método precisa responder a uma pergunta.

## 9. Avaliação e robustez

-   [ ] Justificar a escolha do algoritmo e dos hiperparâmetros.
-   [ ] Comparar soluções alternativas quando isso ajudar a avaliar
    robustez.
-   [ ] Avaliar sensibilidade à seleção de variáveis, tratamento de
    ausentes, escala e métrica.
-   [ ] Verificar se grupos muito pequenos são artefatos ou perfis
    plausíveis.
-   [ ] Não interpretar silhouette alto como prova de validade
    substantiva.
-   [ ] Se usar classificação, separar treino/teste, usar validação
    cruzada e reportar métricas adequadas (incluindo matriz de confusão
    e métricas por classe).
-   [ ] Considerar pesos e desenho amostral na inferência; algoritmos de
    ML convencionais nem sempre incorporam o desenho complexo.
-   [ ] Registrar limitações e resultados negativos.

## 10. Interpretação e conexão com a pesquisa maior

-   [ ] Explicar quais barreiras e condições de infraestrutura aparecem
    associadas à interoperabilidade.
-   [ ] Distinguir infraestrutura disponível, adoção de sistemas,
    capacidade de troca e interoperabilidade efetiva.
-   [ ] Não concluir que blockchain é necessária, viável ou inviável
    apenas com a TIC Saúde.
-   [ ] Relacionar resultados à RNDS e aos padrões de interoperabilidade
    (por exemplo, HL7 FHIR) como contexto, sem alegar que o dataset mede
    conformidade técnica se não medir.
-   [ ] Formular implicações para pesquisas futuras sobre arquitetura,
    governança, segurança, privacidade e integração.
-   [ ] Explicitar que a TIC Saúde caracteriza condições e associações;
    não testa diretamente desempenho, custo ou viabilidade de uma
    solução blockchain.

## 11. Entregáveis do seminário

-   [ ] Notebook Google Colab reproduzível, com etapas, comentários e
    conclusões.
-   [ ] PowerPoint com pergunta, relevância, dataset, metodologia,
    resultados, interpretação e limitações.
-   [ ] Citações da fonte, documentação metodológica e literatura
    utilizada.
-   [ ] Registrar versões de bibliotecas e semente aleatória quando
    aplicável.
-   [ ] Garantir que gráficos e tabelas tenham título, unidade, universo
    e notas metodológicas.
-   [ ] Revisar consistência entre notebook e apresentação.
-   [ ] Não preparar artigo científico: o enunciado não o exige.

## 12. Estrutura sugerida do projeto

``` text
seminario-tic-saude/
├── README.md
├── docs/
│   ├── direcionamento_pesquisa.md
│   ├── dicionario_analitico.md
│   └── decisoes_metodologicas.md
├── data/
│   ├── raw/
│   │   └── original/          # ZIPs e arquivos originais, sem alteração
│   ├── reference/             # dicionário, questionário, relatórios, tabelas oficiais
│   └── processed/             # bases derivadas e documentadas
├── notebooks/
│   ├── 01_entendimento_dos_dados.ipynb
│   ├── 02_preparacao_e_eda.ipynb
│   ├── 03_mineracao_perfis.ipynb
│   └── 04_validacao_e_resultados.ipynb
└── outputs/
    ├── figures/
    └── tables/
```

## Critério de conclusão

O seminário estará metodologicamente consistente quando a pergunta
estiver alinhada às variáveis observadas, o desenho amostral e as
limitações estiverem documentados, as transformações forem
reproduzíveis, a técnica escolhida tiver justificativa e os resultados
responderem à pergunta sem extrapolar o que os dados permitem afirmar.
