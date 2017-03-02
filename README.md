# causalTree Introduction

The _causalTree_ function builds a regression model and returns an _rpart_ object, which is the object derived from _rpart_ package, implementing many ideas in the CART (Classification and Regression Trees), written by Breiman, Friedman, Olshen and Stone. Like _rpart_, _causalTree_ builds a binary regression tree model in two stages, but focuses on estimating heterogeneous causal effect.

This repository was forked from [Professor Athey's Github](https://github.com/susanathey/causalTree). This fork of the repository is used for didactic purposes and will generally not be up to date with the latest version. 

To install this package in R, run the following commands:

```R
install.packages("devtools")
library(devtools) 
install_github("walterwzhang/causalTree")
```

Example usage:

```R
library(causalTree)
set.seed(1234)
CF_fit <- causalForest(y~ x1 + x2 + x3 + x4, data = simulation.1, treatment = simulation.1$treatment,
                   num.trees = 100, verbose = FALSE)
                  
CF_predictions   <-   predict(CF_fit, simulation.2)

summary(CF_predictions)
```

- Remember to set the seed before each `causalForest` run to attain replicable results. 
- For console output for each tree built set the parameter `verbose` to `TRUE` in `casualForest`.
- For more details, please check out briefintro.pdf. 

### Installation FAQ

If the installation of the package with `install_github()` fails. 

- Make sure a prior version of _causalTree_ is not installed. 
- Quit the R/RStudio Session
- Check to see if the _causalTree_ library is still there and delete the folder if it is. (e.g. delete the folder C:\Users\user_name\Documents\R\win-library\3.3\causalTree on a windows computer)
- Open R/RStudio, load _devtools_, and try re-installing this package with `install_github()`

#### References
Susan Athey, Guido Imbens. <b>Recursive Partitioning for Heterogeneous Causal Effects.</b> [<a href="http://arxiv.org/abs/1504.01132">link</a>]
