# Tutorial for root images data analysis

## Introduction 

Here we aim to evaluate the maize plant root elongation from root images.

All measured root shall have been stored in csv file with following format:
![](https://github.com/cndkczy/Tutorial/blob/main/Root/Screenshot.png)

In R make sure isntall Rmisc and ggplot:

    list.of.packages <- c("ggplot2", "Rmisc")
    new.packages <- list.of.packages[!(list.of.packages %in% installed.packages()[,"Package"])]
    if(length(new.packages)) install.packages(new.packages)
