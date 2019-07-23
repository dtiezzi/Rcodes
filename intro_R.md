## R - Introdução
## Tipos de dados, operadores e estruturas de dados em R

Como já vimos em Python, em R os tipos de dados são semelhantes:

```{r}
x = 1L # para formalmente criar uma variável interira usamos o L
y = 1.0
z = 'Bom dia'
w = FALSE

print(c(class(x), class(y), class(z), class(w)))
```

Os operadores numéricos:

```{r}
x = 5
y = 3
x + y # adição
x - y # subtração
x * y # ultiplicação
x / y # divisão
x ^ y # exponencial
x ** y # exponencial
x %% y # modulus
x %/% y # divisão inteira
```

Operadores de atribuição:

```{r}
x = 3
y <- x
print(c(x, y))
```
Operadores de comparação:

```{r}
x == 2
x != 2
x < 2
x > 2
x <= 2
x >= 2
```

Operadores lógicos:
```{r}
x < 2 & x > 0
x < 2 | x > 0
```

### Estruturas de dados

Vetor:

```{r}
v = c(1,3,5)
print(v)
print(v[2]) # em R o índice começa em 1
```

Matriz:

```{r}
m <- matrix(c(1,2,3,4,5,6,7,8,9),3)
m
print(m[2,3]) # indexação da matriz [linha, coluna]
```

Lista:

Listas são um tipo especial de vetor, que podem conter elementos de diferentes tipos, incluindo vetores.

```{r}
a = c(1,3,4)
b =  'bom dia'
c = c('segunda', 'quarta')

l1 = list(a, b, c)
print(l1)

l1[[1]]
```

Os elementos da lista podem receber nomes:
```{r}
l2 = list(Nome = c("Daniel", "Isabela", "José"), Idade = c(45, 21, 12))
l2
l2$Nome
l2$Idade
```
Data frame: é a estrutura de uma tabela com linhas e colunas

```{r}
df <- data.frame(Nome = c("Daniel", "Isabela", "José"), Idade = c(45, 21, 12))
dim(df)
df$Nome
df$Idade
```

## Controle de fluxo e estruturas de repetição

If .. else

```{r}
x = 2
y = 5
if (x * y < 0) {
  z = x * y
} else if (x * y >= 0 & x * y < 10){
  z = x ^ y
} else {
  z = x / y
}
print(z)
```

For e while loops

```{r}
for (i in 1:10) {
  print(i)
}

v1 = c("a", "b", "c")
for (i in v1) {
  print(i)
}
n = 0 # contador
while (n < 5) {
  print("Hello world!")
  n = n+1
}
```

## Funções

```{r}
soma <- function(x, y) {
  return(x + y)
}
s = soma(3, 5)
print(s)
```
