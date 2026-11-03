# Regressão Logística

## 1. Contexto Histórico

No século XIX, o matemático **Pierre François Verhulst** desenvolveu a função logística para estudar o crescimento populacional.

Atualmente, a Regressão Logística é utilizada na Ciência de Dados para calcular probabilidades e classificar informações.

---

## 2. O que é Regressão Logística?

A **Regressão Logística** é um algoritmo de Machine Learning supervisionado que calcula a probabilidade de um acontecimento.

**Exemplo:** prever se um aluno será aprovado considerando suas horas de estudo.

| Variável | Significado |
|---|---|
| X | Horas de estudo |
| Y = 0 | Reprovado |
| Y = 1 | Aprovado |

### Diferença entre Regressão Linear e Logística

| Regressão Linear | Regressão Logística |
|---|---|
| Prevê valores numéricos | Prevê probabilidades |
| Utiliza uma reta | Utiliza uma curva sigmoide |
| Exemplo: prever uma nota | Exemplo: prever aprovação |

---

## 3. Como Funciona?

A Regressão Logística utiliza duas equações principais.

### 3.1. Equação Linear

**z = b₀ + b₁ × x**

Onde:

- **b₀:** intercepto;
- **b₁:** coeficiente da variável;
- **x:** valor de entrada;
- **z:** resultado da equação.

### 3.2. Função Sigmoide

**P = 1 / (1 + e⁻ᶻ)**

A função sigmoide transforma o resultado de `z` em uma probabilidade entre 0 e 1.

O valor de **e** é aproximadamente 2,71828.

### 3.3. Classificação

Utilizando um limite de 50%:

- **P < 0,5:** Reprovado;
- **P ≥ 0,5:** Aprovado.

---

## 4. Como o Modelo Aprende?

O treinamento encontra os valores de **b₀ e b₁** utilizando os dados conhecidos.

O processo é:

1. Receber os dados.
2. Calcular as probabilidades.
3. Comparar as previsões com os resultados reais.
4. Ajustar os coeficientes para reduzir a perda.
5. Repetir até atingir um critério de parada.

Depois do treinamento, o modelo utiliza os coeficientes encontrados para realizar novas previsões.

---

## 5. Exemplo de Cálculo

Considere os coeficientes ilustrativos:

**b₀ = −4**

**b₁ = 1**

Queremos calcular a probabilidade de aprovação para **5 horas de estudo**.

**Etapa 1 — Calcular z**

z = −4 + 1 × 5

**z = 1**

**Etapa 2 — Calcular a probabilidade**

P = 1 / (1 + e⁻¹)

P = 1 / (1 + 0,3679)

**P ≈ 0,7311**

**Etapa 3 — Converter para porcentagem**

P = 0,7311 × 100

**P ≈ 73,11%**

**Resultado:** o modelo estima 73,11% de probabilidade de aprovação e classifica o aluno como aprovado.

---

# Atividade Prática — Google Colab

**Objetivo:** treinar um modelo de Regressão Logística para prever a aprovação de alunos.

Acesse [Google Colab](https://colab.research.google.com/) e crie um notebook.

## Parte 1 — Criar os Dados

```python
import pandas as pd

dados = pd.DataFrame({
    "horas": [1, 2, 3, 4, 5, 6, 7, 8],
    "aprovado": [0, 0, 0, 1, 0, 1, 1, 1]
})

display(dados)
```

**Explicação:** o Pandas organiza os dados em uma tabela. Cada linha representa um aluno.

## Parte 2 — Treinar o Modelo

```python
from sklearn.linear_model import LogisticRegression

X = dados[["horas"]]
y = dados["aprovado"]

modelo = LogisticRegression()
modelo.fit(X, y)

print("b0:", modelo.intercept_[0])
print("b1:", modelo.coef_[0][0])
```

**Explicação:** o método `fit()` treina o modelo e encontra os coeficientes.

## Parte 3 — Calcular as Probabilidades

```python
novos = pd.DataFrame({"horas": [3, 5, 7]})

print(modelo.predict_proba(novos)[:, 1])
print(modelo.predict(novos))
```

**Explicação:**

- `predict_proba()` calcula as probabilidades de aprovação.
- `predict()` apresenta as classificações (0 ou 1).

## Parte 4 — Construir o Gráfico

```python
import matplotlib.pyplot as plt

x = pd.DataFrame({"horas": range(1, 9)})
p = modelo.predict_proba(x)[:, 1]

plt.scatter(dados["horas"], dados["aprovado"])
plt.plot(x["horas"], p)
plt.xlabel("Horas de estudo")
plt.ylabel("Probabilidade")
plt.grid()
plt.show()
```

**Explicação:** os pontos representam os resultados reais e a linha representa as probabilidades estimadas pelo modelo.

## Parte 5 — Análise

Responda no Google Colab:

1. Quais foram os valores encontrados para b₀ e b₁?
2. Qual é a probabilidade de aprovação para 5 horas?
3. Qual é a classificação para 3, 5 e 7 horas?
4. O que acontece com a probabilidade quando aumentam as horas de estudo?

### Entrega

Compartilhar o link do Google Colab contendo o código executado, o gráfico e as respostas.

---

# Conteúdo Extra — Fórmulas e Ordem de Resolução

As fórmulas abaixo apresentam a sequência de treinamento da Regressão Logística Binária utilizando **Gradiente Descendente**, sem regularização.

### 1. Inicializar os Coeficientes

**b₀ = 0**

**b₁ = 0**

Define os valores iniciais para começar o treinamento.

### 2. Calcular z

**zᵢ = b₀ + b₁ × xᵢ**

Calcula o resultado da equação linear para cada observação.

### 3. Calcular a Probabilidade

**Pᵢ = 1 / (1 + e⁻ᶻⁱ)**

Transforma o valor de z em uma probabilidade entre 0 e 1.

### 4. Calcular a Função de Perda

**J = −(1/n) × Σ [yᵢ × ln(Pᵢ) + (1 − yᵢ) × ln(1 − Pᵢ)]**

Mede a perda média das probabilidades previstas.

Onde:

- **n:** quantidade de observações;
- **yᵢ:** resultado real;
- **Pᵢ:** probabilidade prevista;
- **ln:** logaritmo natural;
- **Σ:** somatório.

### 5. Calcular os Gradientes

**Gradiente de b₀:**

**∂J/∂b₀ = (1/n) × Σ(Pᵢ − yᵢ)**

**Gradiente de b₁:**

**∂J/∂b₁ = (1/n) × Σ[(Pᵢ − yᵢ) × xᵢ]**

Os gradientes indicam como modificar os coeficientes para reduzir a perda.

### 6. Atualizar os Coeficientes

**b₀(novo) = b₀(atual) − α × (∂J/∂b₀)**

**b₁(novo) = b₁(atual) − α × (∂J/∂b₁)**

Onde **α** representa a taxa de aprendizado.

Essa etapa ajusta os coeficientes.

### 7. Repetir o Treinamento

Repetir as etapas **2 a 6** até atingir um critério de parada.

### 8. Calcular uma Nova Probabilidade

Com os coeficientes treinados:

**z = b₀ + b₁ × x**

**P = 1 / (1 + e⁻ᶻ)**

Calcula a probabilidade para uma nova entrada.

### 9. Classificar o Resultado

- **P < 0,5:** Classe 0;
- **P ≥ 0,5:** Classe 1.

---

## Resumo das Etapas

| Etapa | Operação | Objetivo |
|---|---|---|
| 1 | Inicializar b₀ e b₁ | Começar o treinamento |
| 2 | Equação linear | Calcular z |
| 3 | Sigmoide | Calcular probabilidade |
| 4 | Função de perda | Medir a perda |
| 5 | Gradientes | Determinar os ajustes |
| 6 | Atualizar coeficientes | Reduzir a perda |
| 7 | Repetir | Treinar o modelo |
| 8 | Calcular z e P | Prever |
| 9 | Aplicar Threshold | Classificar |

**Observação:** o Scikit-learn utiliza, por padrão, regularização e um método de otimização diferente do Gradiente Descendente simples. Os dados apresentados são fictícios e destinados à aprendizagem.
