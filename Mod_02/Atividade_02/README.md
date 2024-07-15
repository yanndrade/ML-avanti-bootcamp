# Resolução da Atividade 02

## Questão 1

```python
def question1(nums: list) -> list:
    ans = []
    for num in nums:
        if num%2 != 0:
            ans.append(num)
    return ans
```

## Questão 2

```python
def question2(nums: list) -> list:
    ans = [1]
    for num in nums:
        lst_divisors = [n for n in range(1,num+1) if num%n == 0]
        if(len(lst_divisors) == 2): 
            ans.append(num)
    return ans
```

## Questão 3

```python
def question3(list1: list, list2: list) -> list:
    ans = []
    for element1 in list1:
        if element1 not in list2:
            ans.append(element1)
    for element2 in list2:
        if element2 not in list1:
            ans.append(element2)
    return ans
```

## Questão 4

```python
def question4(list1: list):
    list1.sort()
    return list1[-2]
```

## Questão 5

```python
def question5(lista: list) -> list:
    # lista = [(Nome, Idade)]
    return sorted(lista, key=lambda x: x[0])
```

## Questão 6

```python
import matplotlib.pyplot as plt
import numpy as np
fig, axs = plt.subplots(ncols=2, nrows=2, figsize=(5.5, 3.5),layout="constrained")
for row in range(2):
    for col in range(2):
        axs[row, col].annotate(f'axs[{row}, {col}]', (0.5, 0.5),
        transform=axs[row, col].transAxes,
        ha='center', va='center', fontsize=18,
        color='darkgrey')
fig.suptitle('plt.subplots()')
```

## Questão 7

```python
import numpy as np
import matplotlib as mpl
import matplotlib.pyplot as plt
x = np.linspace(-2 * np.pi, 2 * np.pi, 100)
y = np.sin(x)
fig, ax = plt.subplots()
ax.plot(x, y)
```

## Questão 8

```python
import pandas as pd

df = pd.read_csv("data.csv")
df.head()
```

## Questão 9

### Para selecionar uma coluna específica podemos utilizar a notação de colchetes [] ou a função .loc[] do pandas.

```python
# Selecionando uma coluna específica com notação de colchetes []

df_column = df['nome_da_coluna']


# Selecionando uma coluna específica com a função .loc[]
df_column = df.loc[:, 'nome_da_coluna']

```

## Questão 10

### Podemos lidar com dados ausentes usando diversas técnicas, como:

- Remover as linhas com dados ausentes: df.dropna()
- Substituir os dados ausentes por um valor específico: df.fillna(valor_substituto)
- Utilizar algoritmos de imputação de dados, como o K-NN (K-nearest neighbors) ou o método de interpolação linear etc.


```python
# 1. Remover as linhas com dados ausentes: df.dropna()

df_novo = df.dropna()

# 2. Substituir os dados ausentes por um valor específico: df.fillna(valor_substituto)

df_novo = df.fillna(0)

```