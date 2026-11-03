# Diagnostico-Regressao-Linear

> Atividade desenvolvida para a disciplina de Métodos Quantitativos para Análise Multivariada (ACH2036) da Escola de Artes, Ciências e Humanidades da Universidade de São Paulo (EACH-USP).

Este repositório armazena os notebooks e conjuntos de dados utilizados para a aplicação prática de Modelos de Regressão Linear Simples. O projeto foca no diagnóstico estatístico da qualidade do ajuste através da análise de resíduos e na exploração de técnicas de transformação de escala para estabilizar a variância e linearizar relações entre variáveis, garantindo o cumprimento das premissas clássicas (LINE).   

---

## 📑 Sumário

* [Estrutura do Repositório](#estrutura-do-repositório)
* [Tecnologias Utilizadas](#-tecnologias-utilizadas)
* [Conjuntos de Dados e Análises](#-conjuntos-de-dados-e-analises)
* [Metodologia Aplicada](#-metodologia-aplicada)
* [Como Executar o Projeto](#-como-executar-o-projeto)


---

## Estrutura do Repositório

```
Diagnostico-Regressao-Linear/
├── datasets/
│   ├── alligator.txt
│   ├── ConcPatog.txt
│   └── treadwear.txt
├── notebooks/
│   ├── 01_02_EDA_Regressao.ipynb # Treadwear e Alligators
│   └── 03_EDA_Regressao_Patogenos.ipynb # ConcPatog
├── .env.example # Modelo do arquivo de configuração local
├── .gitignore
├── requirements.txt
└── README.md
```

---

## Tecnologias Utilizadas

As análises exploratórias, transformações matemáticas e o ajuste dos modelos de regressão foram desenvolvidos na linguagem Python (via Jupyter Notebook / Google Colab), utilizando as seguintes bibliotecas:

* **Pandas**: Manipulação e estruturação dos dados em DataFrames
* **NumPy**: Operações matemáticas vetorizadas para aplicação das transformações de escala.
* **Matplotlib & Seaborn**: Construção de todas as visualizações de dados (gráficos de dispersão, histogramas, etc).
* **Statsmodels**: Ajuste das regressões lineares pelo método dos Mínimos Quadrados Ordinários (OLS), extração do R² ajustado, coeficientes e testes de significância.
* **SciPy**: Diagnóstico de resíduos, plotagem de QQ-Plots e execução do teste de normalidade de Shapiro-Wilk.
* **Scikit-Learn**: Implementações complementares de machine learning para os modelos lineares.
* **python-dotenv**: Leitura do caminho da pasta de dados a partir de um arquivo `.env`, evitando caminhos fixos da máquina de quem desenvolveu.

Todas as dependências estão listadas no arquivo [`requirements.txt`](requirements.txt).

---

## Conjuntos de Dados e Análises

O trabalho investiga cenários onde o ajuste linear direto se mostra problemático, aplicando correções em três bases de dados distintas:   

* **Treadwear:** Investigação da relação entre a quilometragem percorrida (variável preditora) e o desgaste/profundidade do sulco de pneus (variável resposta).
* **Alligators:** Estudo biológico focado na modelagem do peso de jacarés (variável resposta) a partir do seu comprimento (variável preditora).
* **ConcPatog:** Análise ambiental que estima a concentração do Patógeno 2 a partir da concentração do Patógeno 1 em amostras de esgoto submetidas a diferentes estágios de tratamento.

---

## Metodologia Aplicada

Para cada conjunto de dados, os notebooks implementam um pipeline estatístico:

* **Análise de Regressão Preliminar**: Ajuste do modelo OLS sobre os dados na escala original.
* **Diagnóstico de Resíduos**: Avaliação gráfica e analítica das premissas LINE (Função Linear, Erros Independentes, Distribuição Normal, Variância Igual/Homocedasticidade).
* **Exploração de Transformações**: Testes sistemáticos combinando Raiz Quadrada, Quadrado e Logaritmo (base 10) nas variáveis independentes e dependentes.
* **Modelo Otimizado**: Seleção da melhor transformação de escala para corrigir curvaturas e assimetrias, gerando um novo ajuste linear validado estatisticamente.

---

## Como Executar o Projeto

### Pré-requisitos

* Ter o **Python 3.10+** instalado na sua máquina ou utilizar a plataforma Google Colab.
### Clonar o repositório

```bash
git clone https://github.com/beatriz7227/Diagnostico-Regressao-Linear.git
```

```bash
cd Diagnostico-Regressao-Linear
```

### Instalar as dependências

```bash
pip install -r requirements.txt
```

### Configurar o caminho dos dados

Os notebooks leem os arquivos da pasta `datasets/` usando a variável `DATA_DIR`. Se você mantiver a estrutura de pastas do repositório, **não precisa configurar nada**: por padrão, os notebooks procuram os dados em `../datasets`.

Caso queira usar outra pasta, copie o modelo .env.example e edite o caminho:

```
DATA_DIR=C:/caminho/pasta/datasets
```

### Executar os notebooks

```bash
jupyter notebook
```

* Abra os notebooks contidos na pasta `notebooks/` e execute as células sequencialmente para reproduzir as análises, os ajustes de regressão (OLS) e os diagnósticos de resíduos.
