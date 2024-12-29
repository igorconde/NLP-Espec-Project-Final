
# Análise de Sentimentos em Avaliações de Produtos

Este projeto explora o **Processamento de Linguagem Natural (NLP)** e técnicas modernas de aprendizado de máquina para realizar a análise de sentimentos em avaliações de produtos da **Amazon**. O objetivo principal é classificar os sentimentos em três categorias: **positivo**, **negativo** e **neutro**, além de fornecer insights úteis para empresas e consumidores.

---

## 📋 Sumário
- [Análise de Sentimentos em Avaliações de Produtos](#análise-de-sentimentos-em-avaliações-de-produtos)
  - [📋 Sumário](#-sumário)
  - [📌 Visão Geral](#-visão-geral)
  - [📂 Dataset](#-dataset)
    - [Fontes de Dados:](#fontes-de-dados)
    - [Principais Colunas:](#principais-colunas)
  - [🛠 Metodologia](#-metodologia)
    - [Pré-Processamento:](#pré-processamento)
  - [🔍 Análise Exploratória de Dados](#-análise-exploratória-de-dados)
    - [Distribuição de Notas:](#distribuição-de-notas)
    - [Palavras-Chave:](#palavras-chave)
    - [Insights:](#insights)
  - [🧠 Técnicas Utilizadas](#-técnicas-utilizadas)
    - [Modelagem de Tópicos:](#modelagem-de-tópicos)
    - [Classificação de Sentimentos:](#classificação-de-sentimentos)
  - [⚙️ In-Context Learning](#️-in-context-learning)
    - [Aplicação:](#aplicação)
    - [Benefícios:](#benefícios)
  - [📊 Resultados](#-resultados)
    - [Métricas de Avaliação:](#métricas-de-avaliação)
    - [Desafios:](#desafios)
  - [🚀 Como Executar o Projeto](#-como-executar-o-projeto)
  - [🤝 Contribuições](#-contribuições)
  - [📜 Licença](#-licença)
  - [🔗 Contato](#-contato)

---

## 📌 Visão Geral

O projeto busca utilizar NLP para analisar avaliações de produtos com as seguintes finalidades:

1. **Classificação de Sentimentos**: Positivo, Negativo e Neutro.
2. **Insights para Negócios**: Identificar padrões e preferências do consumidor.
3. **Metodologias Avançadas**: Uso de técnicas como BERT, LDA e In-Context Learning.

A proposta é relevante para empresas que desejam **melhorar a experiência do cliente** e tomar **decisões baseadas em dados**.

---

## 📂 Dataset

### Fontes de Dados:
1. **Amazon Product Reviews**: 
   - Avaliações extraídas de um único produto na Amazon.
   - **Dimensão**: 913 registros com 10 colunas principais.

2. **Kaggle Dataset**:
   - 568 mil avaliações de produtos variados.
   - Link do dataset: [Kaggle - Amazon Product Reviews](https://www.kaggle.com)

### Principais Colunas:
- `Text`: Texto completo da avaliação.
- `Score`: Nota atribuída ao produto (1 a 5).
- `HelpfulnessNumerator` e `HelpfulnessDenominator`: Indicadores de utilidade da avaliação.

---

## 🛠 Metodologia

### Pré-Processamento:
1. **Limpeza e Normalização**:
   - Remoção de caracteres especiais, números e stopwords.
   - Conversão para letras minúsculas e tokenização.

2. **Representação Vetorial**:
   - Bag of Words (BoW): Frequência de palavras.
   - Embeddings: Relevância semântica das palavras.
   - Lematização: Redução de palavras às suas formas base.

---

## 🔍 Análise Exploratória de Dados

### Distribuição de Notas:
- **Média**: 4,58 (tendência positiva).
- **Mínimo**: 1 (avaliações mais críticas).
- **Máximo**: 5 (avaliações altamente positivas).
- **Desvio Padrão**: 0,71 (baixa variação).

### Palavras-Chave:
- Termos como `cookie`, `love`, `taste` e `good` foram os mais recorrentes, indicando um foco positivo nas avaliações.

### Insights:
- A maioria das avaliações (75%) não recebeu votos úteis (`HelpfulnessNumerator = 0`).

---

## 🧠 Técnicas Utilizadas

### Modelagem de Tópicos:
- **Latent Dirichlet Allocation (LDA)**:
  - Extração de 5 tópicos principais.
  - Cada tópico contém as 10 palavras mais representativas.

### Classificação de Sentimentos:
- **Modelo BERT (Bidirectional Encoder Representations from Transformers)**:
  - Pré-treinado: `bert-base-uncased`.
  - Treinamento por 3 épocas.
  - Otimizador: AdamW.
  - Divisão de Dados: 80% treino e 20% teste.

---

## ⚙️ In-Context Learning

### Aplicação:
Utilizamos o In-Context Learning para adaptar o modelo a novos exemplos sem re-treino. Essa técnica foi aplicada para ajustar a classificação de sentimentos em contextos específicos, como categorias de produtos ou palavras-chave relevantes.

### Benefícios:
- **Flexibilidade**: O modelo aprende diretamente a partir do contexto fornecido.
- **Redução de Tempo**: Não exige retraining completo.

---

## 📊 Resultados

### Métricas de Avaliação:
- **Acurácia Geral**: 98,36%.
- **F1-Score**:
  - Sentimentos Positivos: Excelente desempenho.
  - Sentimentos Neutros/Negativos: Impactados pelo desequilíbrio do dataset.

### Desafios:
- Desequilíbrio nas classes, especialmente para categorias neutras e negativas.

---

## 🚀 Como Executar o Projeto

1. **Clone o Repositório**:
   ```bash
   git clone https://github.com/seu-usuario/sentiment-analysis.git
   cd sentiment-analysis
   ```

2. **Instale as Dependências**:
   Certifique-se de ter o Python 3.9+ instalado.
   ```bash
   pip install -r requirements.txt
   ```

3. **Baixe os Datasets**:
   - Faça o download do dataset no [Kaggle](https://www.kaggle.com) e salve na pasta `datasets`.

4. **Execute o Script Principal**:
   ```bash
   python main.py
   ```

5. **Resultados**:
   - Os resultados estarão disponíveis em gráficos e métricas no console e na pasta `outputs`.

---

## 🤝 Contribuições

Contribuições são bem-vindas! Para colaborar:
1. Faça um fork do projeto.
2. Crie uma branch para suas alterações:
   ```bash
   git checkout -b minha-feature
   ```
3. Envie um Pull Request.

---

## 📜 Licença

Este projeto está licenciado sob a licença MIT. Veja o arquivo [LICENSE](LICENSE) para mais detalhes.

---

## 🔗 Contato

E-mail: [email](mailto:igapc@cin.ufpe.br)  
