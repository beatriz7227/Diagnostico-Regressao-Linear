# Diagnostico-Regressao-Linear

> Atividade desenvolvida para a disciplina de Métodos Quantitativos para Análise Multivariada (ACH2036) da Escola de Artes, Ciências e Humanidades da Universidade de São Paulo (EACH-USP).

Este repositório armazena os notebooks e conjuntos de dados utilizados para a aplicação prática de Modelos de Regressão Linear Simples. O projeto foca no diagnóstico estatístico da qualidade do ajuste através da análise de resíduos e na exploração de técnicas de transformação de escala para estabilizar a variância e linearizar relações entre variáveis, garantindo o cumprimento das premissas clássicas (LINE).   

---

## 📑 Sumário

* [Tecnologias Utilizadas](#-tecnologias-utilizadas)
* [Conjuntos de Dados e Análises](#-conjuntos-de-dados-e-analises)
* [Metodologia Aplicada](#-metodologia-aplicada)
* [Como Executar o Projeto](#-como-executar-o-projeto)

---

## Tecnologias Utilizadas

As análises exploratórias, transformações matemáticas e o ajuste dos modelos de regressão foram desenvolvidos na linguagem Python (via Jupyter Notebook / Google Colab), utilizando as seguintes bibliotecas:

* **Pandas**: Manipulação e estruturação dos dados em DataFrames
* **NumPy**: Operações matemáticas vetorizadas para aplicação das transformações de escala.
* **Matplotlib & Seaborn**: Construção de todas as visualizações de dados (gráficos de dispersão, histogramas, etc).
* **Statsmodels**: Ajuste das regressões lineares pelo método dos Mínimos Quadrados Ordinários (OLS), extração do R² ajustado, coeficientes e testes de significância.
* **SciPy**: Diagnóstico de resíduos, plotagem de QQ-Plots e execução do teste de normalidade de Shapiro-Wilk.
* **Scikit-Learn**: Implementações complementares de machine learning para os modelos lineares.

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

## Como Executar a Aplicação

### Pré-requisitos
* Ter o **Python 3.10+** instalado na sua máquina ou utilizar a plataforma Google Colab.
* Instalar as bibliotecas necessárias. Caso esteja executando localmente, utilize o comando:
  ```bash
  pip install pandas numpy matplotlib seaborn statsmodels scipy scikit-learn
  ```
### Execução Local
* Clone este repositório em sua máquina:
  ```bash
  git clone https://github.com/beatriz7227/Diagnostico-Regressao-Linear.git
  ```
* Navegue até o diretório do projeto e inicie o ambiente do Jupyter:
  ```bash
  jupyter notebook
  ```
* Abra os notebooks contidos na pasta `notebooks/` e execute as células sequencialmente para reproduzir as análises, os ajustes de regressão (OLS) e os diagnósticos de resíduos.
