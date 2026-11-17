# Seminário de Mineração de Dados — TIC Saúde 2025

**Pergunta.** Quais perfis de maturidade tecnológica e de troca eletrônica de informações emergem entre os estabelecimentos de saúde brasileiros, quão estáveis são e a que características institucionais e territoriais estão associados?

## Estrutura

| Caminho | Conteúdo |
|---|---|
| `notebooks/seminario_tic_saude_2025.ipynb` | Notebook único (Colab), já executado, com todas as etapas e conclusões |
| `apresentacao/seminario_tic_saude_2025.pptx` | 12 slides com roteiro de fala nas notas |
| `outputs/figures/` | Figuras geradas pelo notebook |
| `outputs/tables/` | Tabelas geradas pelo notebook (CSV) |
| `tic_saude_2025_estabelecimentos_pós_cec_base_de_microdados/` | Pacote original do Cetic.br, sem alteração |
| `checklist_…md`, `direcionamento_…md` | Planejamento inicial |

## Como executar

- **Colab:** abrir o notebook e rodar tudo. Ele baixa o ZIP oficial do Cetic.br; se o download falhar, pede o upload do CSV.
- **Local:** rodar a partir de `notebooks/`; o CSV é localizado na pasta do projeto. Requer `pandas`, `scikit-learn`, `matplotlib`, `scipy`, `kmodes`.
- Tempo de execução: cerca de 6 minutos (a maior parte é o bootstrap de estabilidade). Semente fixa: 42.

## Fonte

NIC.br / Cetic.br. TIC Saúde 2025 — Estabelecimentos, microdados v1.0 (com tratamento de confidencialidade). Licença CC BY 4.0.
https://www.cetic.br/pt/arquivos/saude/2025/estabelecimentos/ — baixado em 15/11/2026.

## Decisões metodológicas principais

1. Universo: estabelecimentos que usaram Internet nos últimos 12 meses (n = 3.234), o mesmo das tabelas oficiais dos módulos B–H.
2. Atributos de agrupamento: 62 indicadores binários em 6 blocos; 1 = "Sim", 0 = demais respostas. Sem exclusão de registros, sem imputação.
3. Fora do agrupamento, para validação externa: `C8` (troca sistema-a-sistema) e `C9` (RNDS). Fora, para caracterização: esfera, tipo, UBS, região.
4. Algoritmo principal: k-means com k = 4 (em dados 0/1, distância euclidiana² = Hamming). Comparado com k-modes, Ward, k-means ponderado e k-means em escores de bloco.
5. Clustering sem pesos amostrais; prevalências e caracterização ponderadas. Margens de erro por réplicas, multiplicadas por 1,16 para igualar as margens oficiais nos casos conferidos.
