# Describing data Project

project<- read.csv("C:/Users/anamu/OneDrive/Documents/Capstone Project/Capstone Project/train.csv",  header=T)

#Examine the contents
#SE eliminara la columna Id

project = subset(project, select = -c(Id))

names(project) 
summary(project)
str(project)
head(project)
tail(project)
length(project)
dim(project)
nrow(project)
ncol(project)
#project[complete.cases(project),]
#project[!complete.cases(project),]


install.packages("pastecs")
library(pastecs)
stat.desc(project)


#MSSubClass
round(stat.desc(project[,c("MSSubClass")]),0)
table(project$MSSubClass)
max(table(project$MSSubClass))
min(table(project$MSSubClass))
with(project, hist(MSSubClass, breaks="FD", col="blue",  main = "Building Class", xlab = "Building Subclass"))


#MSZoning

table(project$MSZoning)
max(table(project$MSZoning))
min(table(project$MSZoning))
barplot(table(project$MSZoning),col=c("blue","grey","brown","green","red"),main="General Zoning Classification",  xlab = "Zoning Classification") 


#LotFrontage
with(project, hist(LotFrontage, breaks="FD", col="green",  main = "Linear feet of street connected to property", xlab = "Linear Feet"))
round(stat.desc(project[,c("LotFrontage")]),0)


#LotArea
with(project, hist(LotArea, breaks="FD", col="Yellow",  main = "Lote Area in Square Feet", xlab = "Lote Area"))
round(stat.desc(project[,c("LotArea")]),0)




#Street
table(project$Street)
max(table(project$Street))
min(table(project$Street))
barplot(table(project$Street),col=c("blue","red"),main="Type of Road Acces",  xlab = "Type or Road") 

#Alley

table(project$Alley)
max(table(project$Alley))
min(table(project$Alley))
barplot(table(project$Alley),col=c("brown","yellow"),main="Type of Alley Acces",  xlab = "Type or Alley") 

#LotShape
table(project$LotShape)
max(table(project$LotShape))
min(table(project$LotShape))
barplot(table(project$LotShape),col=c("blue","green", "red","grey"),main="General shape of property",  xlab = "Shape of the Property") 


#LandContour
table(project$LandContour)
max(table(project$LandContour))
min(table(project$LandContour))
barplot(table(project$LandContour),col=c("green","grey", "red","blue"),main="Flatness of the property ",  xlab = "Types of Flatness") 

