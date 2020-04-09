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

```