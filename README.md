# 📊 Financial Anomaly Pipeline: Detecção de Fraudes em Transações Financeiras

Projeto de análise de dados e Machine Learning para identificar anomalias em transações financeiras, com foco no tratamento de classes desbalanceadas.

## 🎯 Contexto e Desafio de Negócio

Em problemas de fraude, transações legítimas podem superar significativamente as fraudulentas. Nesse cenário, a acurácia isolada pode ser enganosa: um modelo que classifique tudo como legítimo pode ter alta acurácia e ainda deixar de detectar fraudes. Este pipeline avalia principalmente **Recall** e **F2-Score**, métricas que ajudam a medir a captura de fraudes e a reduzir falsos negativos.

## 🛠️ Estrutura e Ferramentas

O projeto está documentado em um notebook, desenvolvido para execução no Google Colab.

```text
financial-anomaly-pipeline/
├── .gitignore
├── README.md
├── requirements.txt
└── notebooks/
    └── fraud_detection_anomaly_pipeline.ipynb
```

### Tecnologias

- **Ambiente:** Google Colab
- **Linguagem:** Python 3
- **Dados:** Pandas e NumPy
- **Machine Learning e amostragem:** Scikit-learn e imbalanced-learn (SMOTETomek)
- **Classificação:** XGBoost
- **Visualização:** Matplotlib e Seaborn

## 📈 Etapas do Pipeline

1. **Carga e auditoria:** leitura do CSV hospedado publicamente e inspeção inicial dos dados.
2. **Limpeza:** remoção da coluna `Unnamed: 0`, quando presente, e preparação do alvo.
3. **Pré-processamento:** codificação de variáveis categóricas e aplicação de `StandardScaler` após a divisão entre treino e teste.
4. **Balanceamento:** aplicação de SMOTETomek aos dados de treino.
5. **Modelagem:** comparação entre Isolation Forest e XGBoost. O limiar de decisão do XGBoost está definido em `0.35` para favorecer o Recall.
6. **Avaliação:** geração de matrizes de confusão, comparação de F2-Score, curva Precision-Recall e relatórios de classificação.

## 🏆 Avaliação

O notebook calcula as métricas para as abordagens Isolation Forest e XGBoost. O limiar `0.35` é uma escolha fixa no código; o relatório final e o dashboard permitem avaliar seu efeito sobre Recall e precisão.

## 🚀 Como Executar

1. Clone o repositório:

   ```bash
   git clone https://github.com/MarcosWinther/financial-anomaly-pipeline.git
   cd financial-anomaly-pipeline
   ```

2. Crie e ative um ambiente virtual:

   ```bash
   python -m venv venv
   # Linux/macOS:
   source venv/bin/activate
   # Windows:
   .\venv\Scripts\activate
   ```

3. Instale as dependências:

   ```bash
   pip install -r requirements.txt
   ```

4. Para executar no Google Colab, faça upload de `notebooks/fraud_detection_anomaly_pipeline.ipynb`. O notebook carrega o dataset pela URL definida no código.

## 👨‍💻 Autor

Marcos Winther

- [GitHub](https://github.com/MarcosWinther)
- [LinkedIn](https://www.linkedin.com/in/marcoswinthersilva/)
