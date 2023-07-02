# SQL
[Thiago Klebis](linkedin.com/in/thiagoklebis/)
> Visualização dos primeiros registros: Para ter uma visão inicial dos dados, utilize-se a consulta para exibir os 10 primeiros registros da tabela "credito".
```python
SELECT * FROM credito LIMIT 10
```
![1](https://github.com/TKlebis/SQL-PROJETO/assets/130613291/9e2c84db-d62e-40bb-965f-56b8ab91f486)

>Contagem total de registros: Para determinar o tamanho da tabela "crédito", utilize-se a consulta creditopara obter o número total de registros.

```python
SELECT COUNT(*) FROM
```
![2](https://github.com/TKlebis/SQL-PROJETO/assets/130613291/8c5f94ea-f58a-4354-bde2-b1edc7d176e8)

>Valores únicos de escolaridade: Usando a consulta, extraiu-se uma lista dos valores únicos presentes na coluna "escolaridade" da tabela "crédito".

```python
SELECT DISTINCT escolaridade FROM credito
```

![3](https://github.com/TKlebis/SQL-PROJETO/assets/130613291/2cb916a3-fee4-4299-a8c5-5c693b1c2a83)

>Contagem por salário anual: Com o objetivo de analisar a relação entre o salário anual e a quantidade de registros, utilizou-se a consulta para obter a contagem de registros para cada valor de salário anual.
```python
 SELECT COUNT(*), salario_anual FROM credito GROUP BY salario_anual
```

![4](https://github.com/TKlebis/SQL-PROJETO/assets/130613291/127b37ac-3076-4328-a0d2-19d6d4f345de)

>Contagem por sexo: Para obter uma visão da distribuição dos registros por sexo, utilize-se a consulta para obter a contagem de registros para cada sexo presente na tabela "crédito".

```python
SELECT COUNT(*), sexo FROM credito GROUP BY sexo
```

![5](https://github.com/TKlebis/SQL-PROJETO/assets/130613291/16c25d7c-031f-492b-aef4-796aba72f80d)

>Maiores limites de crédito por escolaridade, tipo de cartão e sexo: Usando a consulta, foram obtidos os 10 maiores limites de crédito para cada combinação de escolaridade, tipo de cartão e sexo.

```python
SELECT MAX(limite_credito) AS limite_credito, escolaridade, tipo_cartao, sexo FROM credito WHERE escolaridade != 'na' AND tipo_cartao != 'na' GROUP BY escolaridade, tipo_cartao, sexo ORDER BY limite_credito DESC LIMIT 10
```

![6](https://github.com/TKlebis/SQL-PROJETO/assets/130613291/fe8c983b-5b5e-49e2-9079-4f8e5e135577)

>Análise dos valores de transações: Com a finalidade de obter insights sobre os valores de transações nos últimos 12 meses, utilizou-se a consulta para calcular o maior valor gasto, a média e o menor valor gasto, agrupados por sexo.


```python
SELECT MAX(valor_transacoes_12m) AS maior_valor_gasto, AVG(valor_transacoes_12m) AS media_valor_gasto, MIN(valor_transacoes_12m) AS min_valor_gasto, sexo FROM credito GROUP BY sexo
```
![7](https://github.com/TKlebis/SQL-PROJETO/assets/130613291/bcf82b0f-ea88-46df-9558-e1949ec6b0df)

>Análise da quantidade de produtos, valor médio de transações e limite de crédito por sexo e salário anual: Para explorar a relação entre essas variáveis, usei-se a consulta para obter a média da quantidade de produtos, valor médio de transações e limite de crédito , agrupados por sexo e salário anual, ordenados pelo valor médio de transações em ordem decrescente.

```python
SELECT AVG(qtd_produtos) AS qts_produtos, AVG(valor_transacoes_12m) AS media_valor_transacoes, AVG(limite_credito) AS media_limite, sexo, salario_anual FROM credito WHERE salario_anual != 'na' GROUP BY sexo, salario_anual ORDER BY AVG(valor_transacoes_12m) DESC
```
![8](https://github.com/TKlebis/SQL-PROJETO/assets/130613291/f4fc4076-77d8-425e-a0d8-195fc98ab3b7)




