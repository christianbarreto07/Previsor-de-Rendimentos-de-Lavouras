# Previsor-de-Rendimentos-de-Lavouras
Algoritmo Naive Bayes com dados coletados da plataforma kaggle com o intuito de prever rendimentos futuros com base em novos dados.

Fertilizante: Representa a quantidade ou concentração de fertilizante aplicado em algumas unidades.
Temperatura: Condições de temperatura durante o período de cultivo.
Nitrogênio (N): Quantidade de nitrogênio presente no fertilizante ou solo, normalmente medida em libras por acre.
Fósforo (P): Quantidade de fósforo presente no fertilizante ou solo, normalmente medida em libras por acre.
Potássio (K): Quantidade de potássio presente no fertilizante ou solo, normalmente medida em libras por acre.
Rendimento (Q/acre): A quantidade de cultura colhida por acre, normalmente medida em alqueires, toneladas ou outras unidades apropriadas.

Este é um projeto que utiliza dados de rendimento de lavouras disponíveis na plataforma Kaggle para prever o rendimento das lavouras com base em diferentes variáveis como chuvas, temperatura e nutrientes do solo. Vamos analisar passo a passo o código e os processos envolvidos:

Imports: O código começa importando as bibliotecas necessárias para o projeto, como pandas para manipulação de dados e scikit-learn para algoritmos de aprendizado de máquina.

Loading Data: Os dados do CSV rendimento_lav.csv são carregados em um DataFrame do pandas chamado df_rend.

Data Preparation:

df_rend: É utilizado para imprimir os dados das lavouras.
df_rend.describe(): Fornece estatísticas descritivas dos dados, como contagem, média, desvio padrão, mínimo e máximo.
df_rend.tail(): Exibe as últimas 5 linhas dos dados das lavouras.
df_rend[df_rend['Rendimento (Q/acre)'] == 12.000000]: Analisa as lavouras com rendimento máximo para observar os valores das variáveis que geraram esse rendimento.
df_rend[df_rend['Rendimento (Q/acre)'] == 6.000000].describe(): Analisa as lavouras com rendimento mínimo para entender as características associadas a esse baixo rendimento.

Divisão dos previsores e classe:
X_rend e Y_rend: São criadas para armazenar os previsores (variáveis independentes) e a classe (variável dependente) respectivamente.

Divisão das bases de Treinamento e Teste:
Utiliza-se train_test_split para dividir os dados em conjuntos de treinamento e teste para previsores e classe.

Salvando base de dados: Os conjuntos de dados de treinamento e teste são salvos em um arquivo rend_lav.pkl usando a biblioteca pickle.

Naive Bayes:
naive_rend = GaussianNB(): Um classificador Naive Bayes Gaussiano é instanciado.
naive_rend.fit(X_rend_treinamento,Y_rend_treinamento): O modelo é treinado com os dados de treinamento.
previsao = naive_rend.predict(X_rend_teste): O modelo é utilizado para fazer previsões com base nos dados de teste.

Avaliação do modelo:
accuracy_score(Y_rend_teste, previsao): A função accuracy_score é usada para calcular a precisão do modelo, ou seja, a taxa de acerto das previsões em relação aos valores reais de rendimento das lavouras.
Este é um fluxo típico de um projeto de análise de dados e construção de modelos preditivos, desde a preparação dos dados até a avaliação do modelo.
