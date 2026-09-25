# Regressão Linear

## 1. O que é?

A **Regressão Linear** é uma técnica de Machine Learning que aprende a relação entre valores numéricos para realizar uma previsão.

Por exemplo, podemos analisar a relação entre:

- `X` → horas de estudo
- `Y` → nota

A partir de dados conhecidos, o modelo encontra uma reta que representa a tendência dos dados.

### Processo

Dados  
↓  
Identificar a relação  
↓  
Encontrar uma reta  
↓  
Fazer uma previsão

---

## 2. Exemplos

### Exemplo 1 — Relação Linear entre os Dados

Considere os seguintes dados de alunos:

| Aluno | Horas de estudo (X) | Nota (Y) |
|---|---:|---:|
| Ana | 1 | 4 |
| Bruno | 2 | 5 |
| Carlos | 3 | 6 |
| Daniela | 4 | 7 |
| Eduardo | 5 | 8 |

Link: [Representação Gráfica](https://www.geogebra.org/m/f2djzxkd)

Nesse exemplo, conforme as horas de estudo aumentam, as notas também aumentam de forma regular.

Os dados apresentam uma relação linear clara.

A Regressão Linear pode representar essa relação por meio de uma reta:

`ŷ = 3 + x`

---

### Exemplo 2 — Relação Linear com Variações nos Dados

Agora considere um conjunto de dados com seis alunos:

| Aluno | Horas de estudo (X) | Nota (Y) |
|---|---:|---:|
| Ana | 2 | 5 |
| Bruno | 2 | 7 |
| Carlos | 3 | 6 |
| Daniela | 4 | 7 |
| Eduardo | 4 | 9 |
| Fernanda | 5 | 8 |

Link: [Representação Gráfica](https://www.geogebra.org/m/vp9u9e9p)

Observe que existem **horas de estudo repetidas**, mas as notas são diferentes.

Por exemplo:

- Ana e Bruno estudaram `2` horas, mas obtiveram notas diferentes;
- Daniela e Eduardo estudaram `4` horas, mas também obtiveram notas diferentes.

Mesmo com essas variações, podemos observar uma **tendência geral de aumento das notas conforme aumentam as horas de estudo**.

A Regressão Linear procura encontrar uma reta que represente essa tendência geral.

Os pontos não precisam estar exatamente sobre a reta.

Portanto, mesmo quando existem valores repetidos de `X` e diferentes valores de `Y`, é possível encontrar uma **reta que represente a tendência dos dados**.

---

## 3. Equação da Regressão Linear

A equação é:

`ŷ = b₀ + b₁x`

Onde:

| Símbolo | Significado |
|---|---|
| `ŷ` | valor previsto |
| `b₀` | valor inicial da reta (Coenficiente Linear) |
| `b₁` | inclinação da reta (Coeficiente Angular) |
| `x` | valor utilizado na previsão |

---

## 4. Exemplo de previsão

Considere a equação:

`ŷ = 3 + x`

Queremos descobrir a previsão para:

`x = 5`

Substituindo:

`ŷ = 3 + 5`

`ŷ = 8`

Portanto, para `x = 5`, o modelo prevê:

`Y = 8`

---

## 5. Interpretando a inclinação

Considere:

`ŷ = 2 + 3x`

Nesse caso:

`b₀ = 2`

`b₁ = 3`

O valor `b₁ = 3` significa que, para cada aumento de `1` em `X`, o valor previsto de `Y` aumenta `3`.

| X | Y previsto |
|---:|---:|
| 1 | 5 |
| 2 | 8 |
| 3 | 11 |
| 4 | 14 |
| 5 | 17 |

---

## 6. Regressão Linear e dados reais

Em uma situação real, normalmente não recebemos a equação pronta.

Primeiro temos os dados:

- `X` → dados conhecidos
- `Y` → dados conhecidos

Depois, a Regressão Linear encontra uma reta que representa a tendência desses dados.

Essa reta pode ser utilizada para realizar uma estimativa.

---
## 7. Fórmulas

Quando temos os dados de `X` e `Y`, podemos calcular matematicamente os coeficientes da reta:

`ŷ = b₀ + b₁x`

Onde:

- `b₀` → **coeficiente linear** (intercepto)
- `b₁` → **coeficiente angular** (inclinação)

### Coeficiente angular — `b₁`

A fórmula é:

`b₁ = Σ((xᵢ - x̄)(yᵢ - ȳ)) / Σ((xᵢ - x̄)²)`

![](https://i.imgur.com/U2IuKbb.png)

O coeficiente angular indica **quanto Y tende a variar quando X aumenta 1 unidade**.

### Coeficiente linear — `b₀`

Depois de encontrar `b₁`, calculamos:

`b₀ = ȳ - b₁x̄`

![](https://i.imgur.com/VhqAFSu.png)

Onde:

| Símbolo | Significado |
|---|---|
| `xᵢ` | Cada valor de X |
| `yᵢ` | Cada valor de Y |
| `x̄` | Média dos valores de X |
| `ȳ` | Média dos valores de Y |
| `b₁` | Coeficiente angular |
| `b₀` | Coeficiente linear |

### Exemplo

Considere:

| X | Y |
|---:|---:|
| 1 | 4 |
| 2 | 5 |
| 3 | 6 |
| 4 | 7 |
| 5 | 8 |

As médias são:

`x̄ = 3`

`ȳ = 6`

Aplicando a fórmula do coeficiente angular:

`b₁ = Σ((xᵢ - x̄)(yᵢ - ȳ)) / Σ((xᵢ - x̄)²)`

`b₁ = 10 / 10`

`b₁ = 1`

Depois, calculamos o coeficiente linear:

`b₀ = ȳ - b₁x̄`

`b₀ = 6 - (1 × 3)`

`b₀ = 3`

Portanto, a reta encontrada é:

`ŷ = 3 + 1x`

ou simplesmente:

`ŷ = 3 + x`

**Interpretação:** o coeficiente angular `b₁ = 1` indica que, a cada aumento de 1 unidade em `X`, o valor previsto de `Y` aumenta 1 unidade.

---

# Exercício — Regressão Linear

Pesquise as **notas mínimas dos últimos 10 anos** de um curso da **UEPG** e utilize a **Regressão Linear** para identificar a tendência das notas.

### Tarefa

1. Organize os dados em uma tabela com `ano` e `nota mínima`.

2. Considere:

   - `X` = ano
   - `Y` = nota mínima

3. Encontre a equação da Regressão Linear:

   `ŷ = b₀ + b₁x`

4. Utilize a equação para **estimar a nota mínima do próximo ano**.

5. Apresente um gráfico com os dados e a reta de regressão.

### Entrega

- Tabela com os 10 anos;
- Gráfico dos dados;
- Reta de regressão;
- Valores de `b₀` e `b₁`;
- Equação da Regressão Linear;
- Previsão para o próximo ano.
- Entrega em Papel A4
