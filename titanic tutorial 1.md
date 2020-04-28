train.data <- read.csv("./ws/r-lang-ws/titanic_data/train.csv", header = TRUE)
test.data <- read.csv("./ws/r-lang-ws/titanic_data/train.csv", header = TRUE)

test.survived <- data.frame(Survived=rep("None", nrow(test.data)), test.data[,])

data.combined <- rbind(train.data, test.data)

str(data.combined)

train.data$Pclass <- as.factor(train.data$Pclass)
train.data$Survived <- as.factor(train.data$Survived)

length(unique(as.character(train.combined$name)))

train.combined$name <- as.character(train.combined$name)

dup.names <- data.combined[which(duplicated(data.combined$name)), "name"]

data.combined[which(data.combined$name %in% dup.names)]

library(ggplot2)

ggplot2(train.data, aes(x=Pclass, y=Survived)) +
    geom_bar() +
    xlab("Pclass") +
    ylab("Survived") +
    labs("fill=Survived")

