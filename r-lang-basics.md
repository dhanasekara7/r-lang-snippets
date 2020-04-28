# R basics
```r
"
1.0 = numeric
1.0L = integer
1/Inf = 0
"

x <- c(0.5, 0.6)       ## numeric
x <- c(TRUE, FALSE)    ## logical
x <- c(T, F)           ## logical
x <- c("a", "b", "c")  ## character
x <- 9:29              ## integer
x <- c(1+0i, 2+4i)     ## complex

x <- vector("numeric", length = 10)
x
# [1] 0 0 0 0 0 0 0 0 0 0

y <- c(1.7, "a")   ## character
y <- c(TRUE, 2)    ## numeric
y <- c("a", TRUE)  ## character


x <- 0:6
class(x)
#[1] "integer"

as.numeric(x)
#[1] 0 1 2 3 4 5 6

as.logical(x)
#[1] FALSE  TRUE  TRUE  TRUE  TRUE  TRUE  TRUE

as.character(x)
#[1] "0" "1" "2" "3" "4" "5" "6"

#Sometimes, R can’t figure out how to coerce an object and this can result in NAs being produced.

x <- c("a", "b", "c")
as.numeric(x)
Warning: NAs introduced by coercion
[1] NA NA NA
as.logical(x)
[1] NA NA NA
as.complex(x)
Warning: NAs introduced by coercion
[1] NA NA NA
```
## R matrices
```r

m <- matrix(nrow = 2, ncol = 3)
m
     [,1] [,2] [,3]
[1,]   NA   NA   NA
[2,]   NA   NA   NA
dim(m)
[1] 2 3
attributes(m)
$dim
[1] 2 3

m <- matrix(1:6, nrow = 2, ncol = 3)
m
     [,1] [,2] [,3]
[1,]    1    3    5
[2,]    2    4    6

x <- 1:3
y <- 10:12
cbind(x, y)
     x  y
[1,] 1 10
[2,] 2 11
[3,] 3 12
rbind(x, y)
  [,1] [,2] [,3]
x    1    2    3
y   10   11   12

## factor
x <- factor(c("yes", "yes", "no", "yes", "no"))
x
[1] yes yes no  yes no
Levels: no yes

table(x)
x
 no yes
  2   3

x <- factor(c("yes", "yes", "no", "yes", "no"))
x  ## Levels are put in alphabetical order
#This can be important in linear modelling because the first level is used as the baseline level.
#This feature can also be used to customize order in plots that include factors,
#since by default factors are plotted in the order of their levels.
[1] yes yes no  yes no
Levels: no yes
x <- factor(c("yes", "yes", "no", "yes", "no"),
            levels = c("yes", "no"))
x
[1] yes yes no  yes no
Levels: yes no

## Create a vector with NAs in it
x <- c(1, 2, NA, 10, 3)
## Return a logical vector indicating which elements are NA
is.na(x)
[1] FALSE FALSE  TRUE FALSE FALSE
## Return a logical vector indicating which elements are NaN
is.nan(x)
[1] FALSE FALSE FALSE FALSE FALSE
## Now create a vector with both NA and NaN values
x <- c(1, 2, NaN, NA, 4)
is.na(x)
[1] FALSE FALSE  TRUE  TRUE FALSE
is.nan(x)
[1] FALSE FALSE  TRUE FALSE FALSE


x <- data.frame(foo = 1:4, bar = c(T, T, F, F))
x
  foo   bar
1   1  TRUE
2   2  TRUE
3   3 FALSE
4   4 FALSE
nrow(x)
[1] 4
ncol(x)
[1] 2

# data frame creation
read.table

read.csv

data.frame

data.matrix ,
as.matrix

x <- 1:3
names(x)
NULL
names(x) <- c("New York", "Seattle", "Los Angeles")
x
   New York     Seattle Los Angeles
          1           2           3
names(x)
[1] "New York"    "Seattle"     "Los Angeles"


x <- list("Los Angeles" = 1, Boston = 2, London = 3)
x
$`Los Angeles`
[1] 1

$Boston
[1] 2

$London
[1] 3
names(x)
[1] "Los Angeles" "Boston"      "London"

m <- matrix(1:4, nrow = 2, ncol = 2)
dimnames(m) <- list(c("a", "b"), c("c", "d"))
m
  c d
a 1 3
b 2 4

colnames(m) <- c("h", "f")
rownames(m) <- c("x", "z")
m
  h f
x 1 3
z 2 4

| Object      	| Set column names 	| Set row names 	|
|-------------	|------------------	|---------------	|
| data frames 	| names()          	| row.names()   	|
| matrix      	| colnames()       	| rownames()    	|



```