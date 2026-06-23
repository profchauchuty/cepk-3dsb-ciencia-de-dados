# Análise Diagnóstica

## 1. Conceito

A **Análise Diagnóstica** é uma abordagem que busca identificar **por que algo aconteceu** com base em dados históricos.

Seu foco é aprofundar a análise descritiva, investigando **causas, relações e fatores que influenciaram um resultado**.

Ela normalmente utiliza:
- cruzamento de dados
- correlação entre variáveis
- filtros e segmentações
- análise comparativa
- investigação de padrões

---

## 2. Exemplo

Uma loja virtual percebe uma queda nas vendas no mês de abril.

| Mês | Vendas |
|---|---|
| Março | 50.000 |
| Abril | 32.000 |

Após investigação, a empresa identifica:
- redução de campanhas de marketing
- aumento no preço de frete
- menos tráfego no site
- falha em anúncios pagos

Nesse caso, a empresa está realizando uma **análise diagnóstica**, pois busca entender o motivo da queda.

---

## 3. Objetivos

| Objetivo | Exemplo |
|---|---|
| Identificar causas | entender por que vendas caíram |
| Encontrar correlações | relação entre preço e demanda |
| Detectar anomalias | pico incomum de cancelamentos |
| Analisar comportamento | mudança no perfil do cliente |
| Explicar resultados | motivo de aumento ou queda |

---

## 3.1 Identificar Causas

Busca entender os fatores que geraram determinado resultado.

### Exemplo

| Indicador | Resultado |
|---|---|
| Queda de vendas | -30% |

### Causas identificadas
- falta de anúncios
- baixa no tráfego orgânico

---

## 3.2 Encontrar Correlações

Analisa relações entre variáveis.

### Exemplo

| Publicidade | Vendas |
|---|---|
| Alta | Alta |
| Baixa | Baixa |

### Interpretação
Existe relação direta entre investimento em publicidade e vendas.

---

## 3.3 Detectar Anomalias

Identifica comportamentos fora do padrão.

### Exemplo

| Dia | Acessos |
|---|---|
| Segunda | 10.000 |
| Terça | 9.500 |
| Quarta | 35.000 |

### Interpretação
Quarta-feira apresenta um pico incomum que precisa ser investigado.

---

## 3.4 Analisar Comportamentos

Estuda mudanças no comportamento do usuário.

### Exemplo

| Período | Tipo de compra |
|---|---|
| Antes | Produtos físicos |
| Depois | Produtos digitais |

### Interpretação
Mudança de preferência do consumidor.

---

## 3.5 Explicar Resultados

Ajuda a justificar variações em indicadores.

### Exemplo

| Mês | Satisfação |
|---|---|
| Maio | 85% |
| Junho | 70% |

### Explicação possível
- aumento no tempo de entrega
- falhas no atendimento

---

## 4. Recursos Utilizados

| Recurso | Finalidade |
|---|---|
| SQL e consultas | cruzamento de dados |
| BI (Power BI, Tableau) | análise visual |
| Estatística | correlações |
| Segmentação | análise por grupo |
| Dashboards | investigação de métricas |

---

## 5. Perguntas Respondidas

A análise diagnóstica responde perguntas como:

| Pergunta | Resposta possível |
|---|---|
| Por que aconteceu? | queda por falta de anúncios |
| O que causou isso? | aumento de preços |
| Existe relação entre fatores? | sim, entre preço e demanda |
| Qual variável influenciou mais? | marketing |
| O que mudou no comportamento? | preferência do cliente |

---

## 6. Principais Técnicas de Análise

## 6.1 Análise de Correlação

Usada para identificar relação entre variáveis.

### Exemplo

| Investimento em marketing | Vendas |
|---|---|
| Alto | Alto |
| Baixo | Baixo |

### Interpretação
Existe correlação positiva.

---

## 6.2 Análise de Segmentação

Divide os dados em grupos.

### Exemplo

| Segmento | Taxa de cancelamento |
|---|---|
| Novos clientes | 20% |
| Clientes antigos | 5% |

### Interpretação
Novos clientes cancelam mais.

---

## 6.3 Análise de Comparação

Compara períodos ou grupos.

### Exemplo

| Período | Vendas |
|---|---|
| Antes da campanha | 40.000 |
| Depois da campanha | 60.000 |

### Interpretação
A campanha influenciou o aumento.

---

## 7. Exemplo Prático

Uma plataforma de e-commerce percebe aumento no abandono de carrinho.

## Dados coletados

| Fator | Valor |
|---|---|
| Abandono de carrinho | 65% |
| Tempo de carregamento | 6s |
| Frete médio | Alto |
| Cupom ativo | Não |

## Análise diagnóstica

- páginas lentas aumentam abandono
- frete alto reduz conversão
- ausência de cupom diminui incentivo de compra

## Possíveis decisões
- otimizar desempenho do site
- reduzir custo de frete
- ativar cupons promocionais

---

## 8. Vantagens

| Vantagem | Benefício |
|---|---|
| Identifica causas | explica problemas |
| Melhora decisões | ações mais precisas |
| Detecta padrões | entendimento profundo |
| Reduz erros | evita decisões intuitivas |
| Apoia estratégias | planejamento mais eficiente |

---

## 9. Limitações

| Limitação | Explicação |
|---|---|
| Não prevê o futuro | foca no passado |
| Pode ser complexa | exige muitos dados |
| Depende da qualidade dos dados | dados ruins geram análises erradas |

### Exemplo

| Mês | Vendas |
|---|---|
| Janeiro | 10.000 |
| Fevereiro | 7.000 |

A análise pode indicar queda, mas se os dados estiverem incompletos, a conclusão pode ser incorreta.

---

## 10. Resumo

| Elemento | Função |
|---|---|
| Correlação | relacionar variáveis |
| Segmentação | dividir grupos |
| Comparação | analisar diferenças |
| Estatística | validar hipóteses |
| BI | visualizar causas |

## A análise diagnóstica:
- explica por que algo aconteceu
- identifica causas e relações
- investiga padrões e anomalias
- complementa a análise descritiva
- apoia decisões estratégicas

---

> Fontes:
> 
> https://aws.amazon.com/pt/what-is/data-analytics/
> 
> https://www.ibm.com/br-pt/topics/diagnostic-analytics
