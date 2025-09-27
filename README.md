# Ciencia_De_Dados_Analise_Exploratoria_Parte_02

Alunos:
Alberto Zilio
Roni Pereira

## Análise Exploratória para Modelagem – Projeto de Regressão (Preços de Carros)

### Objetivo
Explorar o dataset **Automobile** para entender os fatores que mais influenciam o preço de um carro usado.  
Responder à pergunta: **“Quais variáveis parecem ser as mais promissoras para incluir em nosso futuro modelo?”**

---

## 1️⃣ Carregamento e Diagnóstico

**Reflexão:**  
– O dataset tem 205 registros e 26 colunas.  
– `normalized-losses` é a coluna com mais valores ausentes (~20%). Outras colunas como `bore`, `stroke`, `horsepower`, `peak-rpm` e `price` têm poucos valores ausentes.  
– Convertendo as colunas numéricas para float, o dataset fica pronto para análises.  


## 2️⃣ Análise da Variável-Alvo (price)

**Reflexão:**  
– A distribuição dos preços é assimétrica à direita: maioria dos carros concentrada entre 5.000 e 20.000 dólares e alguns outliers acima de 40.000 dólares.  
– O boxplot confirma presença de outliers em preços altos.  
– Essa assimetria pode afetar a regressão linear (tendência de superestimar outliers); talvez seja necessário transformar o preço ou usar modelos mais robustos.  


## 3️⃣ Relação entre Variáveis Numéricas e o Preço

**Reflexão:**  
– A relação entre **potência (horsepower)** e **preço** é claramente positiva e quase linear: motores mais potentes tendem a ter carros mais caros.  
– A relação entre **consumo (highway-mpg)** e **preço** é negativa: carros que fazem mais milhas por galão tendem a ser mais baratos.  
– Essas duas variáveis são candidatas fortes para o modelo.  


## 4️⃣ Relação entre Variáveis Categóricas e o Preço

**Reflexão:**  
– Fabricantes como **Jaguar**, **Porsche**, **BMW**, **Mercedes-Benz** e **Audi** apresentam as medianas de preço mais altas.  
– A variabilidade de preços difere muito entre fabricantes; alguns têm faixas bem amplas (luxo + modelos básicos).  
– Entre os tipos de carroceria, **convertible** e **hardtop** tendem a ter preços medianos mais altos, enquanto **hatchback** e **sedan** concentram-se em preços mais baixos.  
– Essas categorias podem ajudar o modelo a capturar efeitos de marca e estilo.  


## 5️⃣ Visão Geral com Heatmap


**Reflexão:**  
– As variáveis mais correlacionadas positivamente com `price` são: **engine-size**, **curb-weight**, **horsepower** e **wheel-base**.  
– `highway-mpg` e `city-mpg` têm correlação negativa moderada com `price`.  
– Há correlação alta entre `city-mpg` e `highway-mpg` (ambas consumo), o que pode indicar multicolinearidade se usadas juntas.  



## 6️⃣ Conclusão

### Conclusão – Variáveis Mais Promissoras para o Modelo

**Principais Achados:**
– Preço assimétrico com outliers altos.  
– Potência, tamanho do motor e peso têm forte relação positiva com preço.  
– Consumo (mpg) tem relação negativa com preço.  
– Fabricante e tipo de carroceria também explicam variação de preços.

**3–5 Variáveis mais promissoras para o modelo de regressão:**
1. **engine-size** (tamanho do motor)
2. **horsepower** (potência)
3. **curb-weight** (peso do veículo)
4. **highway-mpg** (consumo em estrada)
5. **make** (fabricante)

**Justificativas:**
– São as variáveis com correlação mais alta (positiva ou negativa) com o preço, confirmadas pelos scatterplots e pelo heatmap.  
– Capturam tanto atributos técnicos do veículo (motor, peso, consumo) quanto aspectos de marca que influenciam valor de mercado.  

