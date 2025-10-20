# Rota-02-BI
Projeto de Business Intelligence da Laboratória - análise, storytelling e dashboard Airbnb
---
## Descrição do Projeto
O projeto **Rota 02 – BI** teve como objetivo aplicar conceitos de **Business Intelligence (Inteligência de Negócios)** para transformar dados em **insights estratégicos** e visuais interativos.  
Exploramos dados do **Airbnb** para construir um painel (**dashboard**) completo com **Data Storytelling**, permitindo compreender melhor a distribuição e o comportamento dos quartos disponíveis.

O projeto foca em:

- Processamento e preparação das bases de dados
- Criação de relações entre tabelas
- Desenvolvimento de novas variáveis e medidas com DAX
- Construção de dashboards interativos com narrativa de dados

---

## Objetivos

- Garantir **consistência e integridade dos dados**
- Relacionar tabelas e criar colunas calculadas
- Aplicar fórmulas DAX para métricas estratégicas
- Explorar dados com análises descritivas, tendências e distribuição
- Construir dashboards claros e interativos
- Aplicar **Data Storytelling** para tomada de decisão

---

## Tecnologias e Ferramentas Utilizadas

- **Plataformas:** Power BI, BigQuery  
- **Linguagens:** DAX, SQL (BigQuery) 
- **Insumos:** Bases de dados do Airbnb  

### Badges
![Power BI](https://img.shields.io/badge/PowerBI-Data%20Visualization-blue)  
![BigQuery](https://img.shields.io/badge/BigQuery-Data%20Warehouse-blueviolet)

---

## Passos do Projeto

### 1️⃣ Processar e Preparar a Base de Dados
- Verificar e alterar tipos de dados das variáveis
- Relacionar tabelas no Power BI
- Criar novas colunas calculadas

### 2️⃣ Utilizar Fórmulas DAX
- Criar colunas e medidas estratégicas
- Calcular métricas de ocupação e disponibilidade
- Explorar a diferença entre medidas, colunas e parâmetros

### 3️⃣ Análise Exploratória de Dados
- Agrupar dados por variáveis categóricas
- Visualizar distribuições e tendências
- Aplicar medidas de tendência central e dispersão

### 4️⃣ Dashboard e Data Storytelling
- Construir painel completo com gráficos e mapas
- Aplicar narrativa de dados para insights claros
- Apresentar recomendações estratégicas

---

## Resultados

- Dashboard completo mostrando:  
  - Distribuição de quartos por bairro  
  - Ocupação e disponibilidade ao longo do ano  
  - Métricas estratégicas calculadas com DAX

- Insights obtidos através de **Data Storytelling**, apoiando decisões baseadas em dados
## Resultados


![Dashboard Página 1](dashboards_screenshots/dashboard_page1n.jpeg.jpg)

### 📈 Dashboards Criados

#### Página 1
- Gráficos incluídos:
  - Potencial anual de hóspedes por bairro
  - Distribuição de acomodações por bairro
  - Tipos de acomodações disponíveis
  - Distribuição dos preços das acomodações
  - Distribuição de avaliações por acomodações
  - Disponibilidade anual das acomodações

![Dashboard Página 2](dashboards_screenshots/dashboard_page2n.jpeg.jpg)

#### Página 2
- Gráficos incluídos:
  - Total de avaliações por ano
  - Preço médio por ano por bairro
  - Disponibilidade média anual por bairro
  - Distribuição geográfica das acomodações


---

###  Medidas DAX Utilizadas

#### 1. Potencial Anual de Hóspedes por Bairro
- **O que faz:** calcula o número total de hóspedes por ano em cada bairro.

```DAX
Potencial Anual de Hóspedes = SUM(Tabela[Hóspedes])
````

#### 2. Distribuição de Acomodações por Bairro

* **O que faz:** conta o número total de acomodações disponíveis em cada bairro.

```DAX
Acomodações por Bairro = COUNTROWS(Tabela)
```

#### 3. Tipos de Acomodações Disponíveis

* **O que faz:** calcula a proporção percentual de cada tipo de acomodação (Casa Completa, Quarto Privativo, Quarto Compartilhado).

```DAX
% Casa Completa = DIVIDE(COUNTROWS(FILTER(Tabela, Tabela[Tipo] = "Casa Completa")), COUNTROWS(Tabela))
```

#### 4. Distribuição dos Preços das Acomodações

* **O que faz:** organiza as acomodações em faixas de preço, mostrando quantas se enquadram em cada faixa.

```DAX
Faixa de Preço = SWITCH(TRUE(),
    Tabela[Preço] <= 50, "Até 50",
    Tabela[Preço] <= 100, "51 a 100",
    Tabela[Preço] <= 150, "101 a 150",
    "Acima de 150"
)
```

#### 5. Distribuição de Avaliações por Acomodações

* **O que faz:** conta a quantidade de acomodações com base no número de avaliações.

```DAX
Avaliações por Acomodações = COUNTROWS(FILTER(Tabela, Tabela[Avaliações] > 0))
```

#### 6. Disponibilidade Anual das Acomodações

* **O que faz:** classifica as acomodações de acordo com sua disponibilidade anual em dias.

```DAX
Faixa de Disponibilidade = SWITCH(TRUE(),
    Tabela[Disponibilidade] <= 30, "Até 30 dias",
    Tabela[Disponibilidade] <= 60, "31 a 60 dias",
    Tabela[Disponibilidade] <= 90, "61 a 90 dias",
    "Acima de 90 dias"
)
```

---

## Como Rodar o Projeto

1. Abrir o Power BI Desktop versão 2.148.878.0 (64-bit, outubro de 2025)
2. Conectar às bases de dados do Airbnb (BigQuery ou CSVs)
3. Criar relações entre tabelas
4. Aplicar fórmulas DAX conforme definido no projeto
5. Construir visualizações e dashboards interativos
6. Explorar insights utilizando Data Storytelling
###  Observação
- Dados utilizados são fictícios e foram criados para fins de demonstração


---

## Autor
**Leticia Gama de Souza**  
[LinkedIn](https://www.linkedin.com/in/leticia-gama-code) | [GitHub](https://github.com/LeticiaGama-dev)

