# R Basics - 1
## Data Types and Structures in R

This is my first post about R and I will be covering an important topic here. R is a object oriented language. What I mean is every variable in R is an object. So, even a simple integer has attributes. The attribute can be `None` or, be a list of attributes including `names`, `dimnames`, `dim` and `class`.

In R, we have some data types. Everyone is an object from a different class. Let's look at the code bellow:

```{r}
# The class character
x <- 'hello R users'
x
```

The `<-` is an assignment signal. You can use  `=` as well.
So, we created an object named `x` and assigned it the value `hello R`. In R, you do not have to explicitly define the type of the object. R takes care of it. In this example, `x` is an object from the **character** class.
So, we can use the `class()` function to get the class of a specific object:

```{r}
class(x)
```

Now, let's create an object from each R class:

**numeric**
```{r}
y <- 10
y
class(y)
```

**integer**
```{r}
z <- 10L # note the L after the integer
z
class(z)
```

**logical**
```{r}
p <- FALSE
q <- T  # you can use the first letter only for logical variable 
p
q
class(c(p,q))
```

**complex**
```{r}
# R can deal with complex numbers as well
r <- 21+2i
r
class(r)
```

In R, we have some data structures as well. They are very powerful objects in terms of data analysis and manipulation. They are `atomic vectors`, `list`, `matrix`, and `data frame`. Let's see how we can create everyone bellow:

**atomic vector or JUST vector**
```{r}
# we can use th c() function to create a vector
v1 <- c(1,2,3,4,5) # a numeric vector
v2 <- c("a", "b", "c", "d")  # a character vector
v1
v2
class(c(v1, v2))
```

**list**
```{r}
l1 <- list(vector = c(1,2,3,4,5), number = 10, logical = TRUE, character= 'hello R users')
l1
# Note I created a list with different class objects inside. You can name every object inside the list, or you can omit the names
l2 <- list(c(1,2,3,4,5), 10, TRUE, 'hello R users')
l2
class(c(l1,l2))
```
**matrix**
```{r}
vals <- rnorm(100, 10, 2)  # the rnorm() function returns random values with a normal distribution.
# The rnorm() function arguments are the number of values (100), the mean (10) and the standard deviation (2)
m <- matrix(vals, 10, 10) # we pass to the matrix() function the values and the matrix dimension
m
class(m)
```

**data frame**
```{r}
cities <- c("Ribeirão Preto", "Presidente Prudente", "Piracicaba", "São Paulo")
population <- c(694534, 207610, 297767, 12176866)
lived <- c("yes", "yes", "no", "yes")
df <- data.frame(City = cities, 
                 Population_2018 = population,
                 Has_lived = lived)
df
class(df)
```

Now I'm showing the attributes these objects have. I'm using the same matrix `m` I've already created. Let's look the object attributes:
```{r}
attributes(m)
```
So, we have only de `dim()` attribute. This returns the dimension of the object:
```{r}
dim(m)
```
It's a 10 x 10 matrix (rows x columns). We can create more attributes to the object:
```{r}
# Creating the rows and columns names 
dimnames(m) <- list(c(paste("L", 1:10, sep = "")), c(paste("C", 1:10, sep = "")))
attributes(m)
```
And we can assign a name for every value in this matrix. I will be using a repetition structure for this. If you are not familiar with this, no worries. We will be covering this in details further:
```{r}
for (i in 1:length(m)) {
names(m)[i] <- paste("val_", i, sep = "")
}
names(m)
```
Basically, I used a for loop to assign a name for every value in the matrix `m`. Now, is possible to access a specific value in the matrix:
```{r}
m["val_57"]
```
And the `m` attributes now is this:
```{r}
attributes(m)
```

So, this is the end of the first tutorial. We covered the basic data types in R. I hope the object oriented concept was clear and helped you to understand how variables are treated in R.

## See you in the next tutorial. CHEERS!
