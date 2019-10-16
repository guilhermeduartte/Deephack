# deephack

### Autores: 
## Lucas Nunes Sequeira, Guilherme Duarte Laurindo de Souza e Ian Lucas Ramos de Carvalho dos Santos Pinto

### Data: 16/10/2019

Automatização da coleta de dados das despesas em 'Gestão Ambiental' para os municípios cobertos pelo Tribunal de Contas do Estado de São Paulo (TCE-SP). *Insights* em análises de dados com visualizações gráficas em séries temporaris, tabelas, pizzas e mapas.

#### Automatização da coleta de dados
Com um comando o usuário consegue coletar as informações das despesas de um município de interesse para um intervalo de anos; com isso todas as visualizações supracitadas estão disponíveis. Além disso, existe a opção de coletar as informações dos k-vizinhos do município com base nas latitudes e longitudes para análises locais. Não só isso como também, é possível automaticamente treinar uma rede recorrente (RNN simples) para predição do comportamento futuro do município em questão.
```
    referencia = readMunicipio('Ilhabela', years = (2016, 2018), k_neighboors=3, trainRNN = True)
```
#### Visualização dos dados
Coletada as informações de um dado município, podem ser feitas visualizações como:
- **Séries temporais:** Representam os gastos totais por mês referente à Gestão Ambiental; e se for feita a opção para o trino automático da RNN, fica visível também a predição futura de um ano para o município em análise.

```
    referencia.plotSerie()
```
<div style="text-align:center"><img src="images/exemplo_serie.png" height="500" /></div>

- **Pizza de descrição:** Já nessa representação, a fins de interesse de explicabilidade em quais programas foram distribuidas as despesas anuais, podemos visualizar em um gráfico de pizza tal distribuição para uma lista de anos.

```
    referencia.plotOverview([2018])
```

<div style="text-align:center"><img src="images/exemplo_overview.png" height="390" /></div>

- **Comparação de despesas locais:** Nessa representação, visualizamos em destaque a despesa *per capita* total para o ano predito do município de referência, com respeito ao último gasto anual dos k-vizinhos da referência.

```
    referencia.plotNeighboorsCompare()
```

<img src="images/exemplo_compare.png" height="390" align="center"/>
    
Dependências:

- pandas
- seaborn
- matplotlib
- numpy
- tensorflow
- pickle
- mplleaflet

<img alt="ObservatórioDoFuturo" src="https://www4.tce.sp.gov.br/observatorio/wp-content/uploads/sites/3/2018/01/logo_splash.png" height="60">

<img alt="ObservatórioDoFuturo" src="http://www4.tce.sp.gov.br/licitacao/sites/licitacao/files/sites/default/files/images/logo-tcesp.png" height="60">
