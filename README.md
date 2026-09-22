# Projeto de Crescimento e Adoção do PIX - Pessoas Físicas e Jurídicas
 
## 📋 Visão Geral do Projeto
 
Este projeto realiza uma análise detalhada do crescimento e adoção do **PIX** (sistema de pagamento instantâneo brasileiro) entre **pessoas físicas (PF)** e **pessoas jurídicas (PJ)** durante o período de **fevereiro de 2022 a janeiro de 2024**.
 
O objetivo principal é entender as tendências de crescimento percentual mensal da adopção do PIX em cada segmento, identificando padrões de comportamento e insights sobre como este novo sistema de pagamento foi adotado pelos diferentes tipos de usuários no Brasil.
 
---
 
## 🎯 Problema Abordado
 
O crescimento do PIX foi exponencial após seu lançamento em novembro de 2020. Este projeto busca responder:
 
- **Como evoluiu o número de contas PIX entre pessoas físicas e jurídicas?**
- **Qual foi a taxa de crescimento percentual mês a mês para cada segmento?**
- **Existem diferenças significativas entre a adoção por PF e PJ?**
- **Quais períodos tiveram maior crescimento?**
Estes insights são valiosos para entender o comportamento do mercado de pagamentos digital no Brasil e apoiar decisões estratégicas de instituições financeiras e fintechs.
 
---
 
## 📊 Exploração de Dados
 
### Fonte de Dados
Os dados utilizados estão no arquivo `data_raw/arq.csv` e contêm:
 
| Campo | Descrição |
|-------|-----------|
| **DateTime** | Data final do mês (formato: YYYY-MM-DD) |
| **Contas - Pessoa Jurídica** | Número total de contas PIX de pessoas jurídicas |
| **Contas - Pessoa Física** | Número total de contas PIX de pessoas físicas |
| **Total** | Somatório total de contas PIX |
 
### Período de Análise
- **Data Inicial:** 28 de fevereiro de 2022
- **Data Final:** 31 de janeiro de 2024
- **Granularidade:** Dados mensais (24 meses)
### Estrutura dos Dados
 
```
DateTime          | Contas - Pessoa Jurídica | Contas - Pessoa Física | Total
2022-02-28        | 12.333.613              | 261.179.373            | 273.512.986
2022-03-31        | 12.912.902              | 271.490.950            | 284.403.852
...
2024-01-31        | 25.652.301              | 461.647.824            | 487.300.125
```
 
---
 
## 🔍 Análise Realizada
 
### Processamento de Dados
 
O projeto utiliza um pipeline em Python (notebook Jupyter) que:
 
1. **Carregamento de Dados:** Lê o arquivo CSV e estrutura os dados em arrays
2. **Segregação de Dados:** Separa as contas por tipo (PF e PJ)
3. **Cálculo de Crescimento:** Calcula o percentual de crescimento mensal para cada segmento
4. **Processamento:** Aplica transformações e gera arquivos processados em `data_processed/arq.csv`
### Fórmula de Crescimento Percentual Mensal
 
```
Crescimento % = ((Contas[Mês N] - Contas[Mês N-1]) / Contas[Mês N-1]) × 100
```
 
### Exemplos de Crescimento Percentual
 
**Pessoas Físicas (PF):**
- Fevereiro → Março 2022: +3,95%
- Março → Abril 2022: +3,61%
- Abril → Maio 2022: +3,93%
**Pessoas Jurídicas (PJ):**
- Fevereiro → Março 2022: +4,70%
- Março → Abril 2022: +5,40%
- Abril → Maio 2022: +5,23%
---
 
## 📈 Principais Insights
 
### Crescimento Comparativo
- **Pessoas Jurídicas (PJ)** apresentaram **taxa de crescimento percentual maior** que Pessoas Físicas (PF) na maioria dos meses
- O crescimento de PJ variou entre 4,7% a 5,4% nos primeiros meses analisados
- O crescimento de PF manteve-se mais estável, entre 3,6% a 3,9% no mesmo período
### Volume Absoluto
- Pessoas Físicas representam a **maioria dos usuários**, com aproximadamente 94% das contas em janeiro de 2024
- Pessoas Jurídicas, apesar de menores em número, crescem percentualmente de forma mais acelerada
### Período Analisado
Durante os 24 meses analisados:
- Total de contas PF cresceu de **261,2 milhões** para **461,6 milhões**
- Total de contas PJ cresceu de **12,3 milhões** para **25,6 milhões**
- Crescimento acumulado: **+77% para PF** e **+108% para PJ**
---
 
## 📁 Estrutura do Projeto
 
```
Projeto_Crescimento_Adocao_PIX_PF_PJ/
├── data_raw/
│   └── arq.csv                          # Dados brutos (24 meses)
├── data_processed/
│   └── arq.csv                          # Dados processados com crescimento %
├── notebook/
│   └── notebook_processor.ipynb          # Pipeline de processamento
├── resources/
│   ├── name_column_pf                   # Identificador coluna PF
│   ├── name_column_pj                   # Identificador coluna PJ
│   ├── name_column_pf_final             # Nome coluna output PF
│   └── name_column_pj_final             # Nome coluna output PJ
├── comments/                             # Comentários e documentação
├── .gitignore
└── README.md                             # Este arquivo
```
 
---
 
## 🚀 Como Usar
 
### Pré-requisitos
- Python 3.8+
- Pandas (recomendado para análises adicionais)
- Jupyter Notebook
### Executar o Processamento
 
1. Navegue até o diretório do projeto:
```bash
cd Projeto_Crescimento_Adocao_PIX_PF_PJ
```
 
2. Abra o notebook Jupyter:
```bash
jupyter notebook notebook/notebook_processor.ipynb
```
 
3. Execute todas as células para processar os dados
4. Os dados processados estarão em `data_processed/arq.csv`
---
 
## 💡 Possíveis Extensões
 
- **Análise de Sazonalidade:** Identificar períodos de pico/baixa adoção
- **Previsão Futura:** Usar modelos de séries temporais para prever crescimento futuro
- **Análise Regional:** Segmentar dados por região/estado (se disponíveis)
- **Análise por Setor:** Para PJ, analisar por segmento de negócio
- **Visualizações Avançadas:** Dashboards interativos com Plotly/Tableau
- **Análise de Saturation:** Estimar quando a adoção chegará ao máximo
---
 
## 📝 Metodologia
 
Este projeto utiliza uma metodologia descritiva, analisando:
 
✅ **Tendências**: Evolução mês a mês do número de contas  
✅ **Crescimento Percentual**: Taxa de variação mensal  
✅ **Comparação Segmentada**: Análise separada de PF vs PJ  
✅ **Período Completo**: Visão de 2 anos de dados históricos  
 
---
 
## 👤 Autor
 
**Gustavo Pacheco**  
Desenvolvedor | Machine Learning Engineer em formação  
F1RST Digital Services
 
---
 
## 📄 Licença
 
Este projeto está disponível como referência pública. 
 
---
 
## 📧 Contato
 
Para dúvidas ou sugestões sobre este projeto, entre em contato através do GitHub.
