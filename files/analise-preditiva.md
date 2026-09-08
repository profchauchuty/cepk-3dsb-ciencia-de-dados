# Análise Preditiva

## 1. Conceito

A Análise Preditiva é uma abordagem da Ciência de Dados utilizada para estimar acontecimentos futuros a partir de dados históricos.

Enquanto outras análises procuram compreender o que já aconteceu, a Análise Preditiva busca responder:

> "O que provavelmente acontecerá?"

Para realizar uma previsão, são utilizados dados do passado para identificar padrões que possam ajudar a estimar um resultado futuro.

### Exemplo

Uma loja possui o seguinte histórico de vendas:

| Mês | Vendas |
|------|---------|
| Janeiro | R$ 20.000 |
| Fevereiro | R$ 25.000 |
| Março | R$ 30.000 |
| Abril | R$ 35.000 |

A empresa deseja saber:

> "Quanto poderá vender em maio?"

A partir dos dados históricos, um modelo preditivo pode realizar uma estimativa.

**Previsão:** R$ 40.000

Essa é uma aplicação de Análise Preditiva.

---

## 2. O que a Análise Preditiva procura responder?

A Análise Preditiva pode ser utilizada para responder diferentes tipos de perguntas.

### Exemplos

- Quanto será vendido?
- O cliente irá comprar?
- O cliente irá cancelar?
- O aluno será aprovado?
- Existe risco de inadimplência?
- Qual será a demanda?
- Qual será o comportamento de um cliente?
- Qual será o valor de uma determinada variável?

A escolha do método depende do tipo de previsão que desejamos realizar.

---

## 3. Prever um Valor

Imagine que uma empresa deseja prever o valor das vendas do próximo mês.

Ela possui os seguintes dados:

| Mês | Investimento em Publicidade | Vendas |
|------|----------------------------|---------|
| Janeiro | R$ 1.000 | R$ 10.000 |
| Fevereiro | R$ 2.000 | R$ 15.000 |
| Março | R$ 3.000 | R$ 20.000 |
| Abril | R$ 4.000 | R$ 25.000 |

A empresa deseja descobrir:

> "Quanto poderá vender se investir R$ 5.000 em publicidade?"

### Método Utilizado: Regressão Linear

A Regressão Linear é adequada quando queremos prever um valor numérico a partir da relação entre variáveis.

Nesse exemplo, podemos utilizar o histórico de investimento e vendas para realizar a previsão.

### Previsão

- Investimento: R$ 5.000
- Vendas previstas: R$ 30.000

**Método:** Regressão Linear

**Objetivo:** prever um valor numérico.

---

## 4. Prever uma Categoria

Agora imagine que uma escola deseja prever se um aluno será aprovado ou reprovado.

A escola possui dados históricos:

| Aluno | Horas de Estudo | Resultado |
|--------|----------------|------------|
| A | 2 | Reprovado |
| B | 4 | Reprovado |
| C | 6 | Aprovado |
| D | 8 | Aprovado |
| E | 10 | Aprovado |

Um novo aluno estudou 7 horas.

A escola deseja saber:

> "Esse aluno provavelmente será aprovado?"

### Método Utilizado: Regressão Logística

A Regressão Logística pode ser utilizada quando queremos realizar uma previsão de classificação, como:

- Sim / Não
- Aprovado / Reprovado
- Compra / Não compra
- Risco / Sem risco

O modelo pode produzir uma probabilidade.

### Previsão

- Probabilidade de aprovação: 82%
- Resultado previsto: Aprovado

**Método:** Regressão Logística

**Objetivo:** prever uma categoria ou probabilidade.

---

## 5. Prever através de Decisões

Imagine uma loja que deseja prever se determinado cliente irá comprar ou não comprar um produto.

A empresa possui informações sobre seus clientes:

- Idade
- Renda
- Número de visitas ao site
- Quantidade de produtos visualizados

### Método Utilizado: Árvore de Decisão

A Árvore de Decisão pode utilizar essas informações para chegar a uma previsão através de uma sequência de decisões.

### Exemplo

```text
             Renda > R$ 3.000?
                 /       \
               Sim       Não
               /           \
       Visitou o site?     Não
          /     \
        Sim     Não
        /        \
     Compra    Não compra
```

### Novo Cliente

- Renda: R$ 4.000
- Visitou o site: Sim

Seguindo as decisões:

```text
Renda > R$ 3.000?
        ↓
       Sim
        ↓
Visitou o site?
        ↓
       Sim
        ↓
     Compra
```

### Previsão

O cliente provavelmente comprará.

**Método:** Árvore de Decisão

**Objetivo:** realizar uma previsão através de decisões baseadas nas características dos dados.

---

## 6. Prever Utilizando Dados Semelhantes

Imagine uma empresa que deseja classificar seus clientes de acordo com o potencial de compra.

Ela possui clientes com características semelhantes registradas em seu banco de dados.

### Método Utilizado: K-Nearest Neighbors (KNN)

O algoritmo KNN compara um novo cliente com clientes já conhecidos e procura aqueles que possuem características mais parecidas.

### Exemplo

| Cliente | Idade | Renda | Classe |
|----------|--------|--------|---------|
| A | 22 | R$ 2.000 | Baixo Potencial |
| B | 25 | R$ 2.500 | Baixo Potencial |
| C | 40 | R$ 6.000 | Alto Potencial |
| D | 45 | R$ 7.000 | Alto Potencial |

Novo cliente:

- Idade: 42 anos
- Renda: R$ 6.500

O algoritmo identifica os clientes mais semelhantes e verifica sua classificação.

### Previsão

Alto Potencial de Compra.

**Método:** KNN (K-Nearest Neighbors)

**Objetivo:** prever uma categoria utilizando exemplos semelhantes.

---

## 7. Resumo dos Métodos Preditivos

| Situação | Método |
|-----------|---------|
| Prever um valor numérico | Regressão Linear |
| Prever uma categoria | Regressão Logística |
| Prever através de regras e decisões | Árvore de Decisão |
| Prever utilizando exemplos semelhantes | KNN |

---

## 8. Conclusão

A Análise Preditiva utiliza dados históricos para estimar resultados futuros.

Diversos algoritmos podem ser utilizados, dependendo do tipo de problema:

- **Regressão Linear** → previsão de valores numéricos.
- **Regressão Logística** → previsão de categorias e probabilidades.
- **Árvore de Decisão** → previsão baseada em regras e decisões.
- **KNN** → previsão baseada em exemplos semelhantes.
