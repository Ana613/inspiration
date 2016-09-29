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

#Utilities
table(project$Utilities)
max(table(project$Utilities))
min(table(project$Utilities))
barplot(table(project$Utilities),col=c("yellow", "green"),main="Utilities",  xlab = "Types of Utilities") 


#LotConfig
table(project$LotConfig)
max(table(project$LotConfig))
min(table(project$LotConfig))
barplot(table(project$LotConfig),col=c("blue2", "darkgoldenrod", "deeppink2", "darkgreen", "cyan"),main="Lote Configuration",  xlab = "Types of Lote Configuration") 


#LandSlope
table(project$LandSlope)
max(table(project$LandSlope))
min(table(project$LandSlope))
barplot(table(project$LandSlope),col=c("darkcyan", "deeppink2", "bisque1"),main="Slopes of the Properties",  xlab = "Types of Slope") 

#Neighborhood
table(project$Neighborhood)
max(table(project$Neighborhood))
min(table(project$Neighborhood))
Neigh <- table(project$Neighborhood)
barplot(Neigh, names= names(Neigh),col=rainbow(25), las=2, main="Neighborhood") 


#Condition1
table(project$Condition1)
max(table(project$Condition1))
min(table(project$Condition1))
Cond1 <- table(project$Condition1)
barplot(Cond1, names= names(Cond1),col=rainbow(9), las=2, main="Proximity to main road or railroad") 


#Condition2
table(project$Condition2)
max(table(project$Condition2))
min(table(project$Condition2))
Cond2<- table(project$Condition2)
barplot(Cond2, names= names(Cond2),col=rainbow(8), las=2, main="Proximity to more than one railroad") 


#BldgType
table(project$BldgType)
max(table(project$BldgType))
min(table(project$BldgType))
barplot(table(project$BldgType),col=rainbow(5),main="Types of Dwelling",  xlab = "Types of Dwelling") 



#HouseStyle
table(project$HouseStyle)
max(table(project$HouseStyle))
min(table(project$HouseStyle))
barplot(table(project$HouseStyle),col=rainbow(8),main="Style of Dwelling",  xlab = "Style of Dwelling") 


#OverallQual
project$OverallQual<-factor(project$OverallQual)
table(project$OverallQual)
max(table(project$OverallQual))
min(table(project$OverallQual))
barplot(table(project$OverallQual),col=rainbow(10),main="Overall quality",  xlab = "Overall material and finish quality") 


#OverallCond
project$OverallCond<-factor(project$OverallCond)
table(project$OverallCond)
max(table(project$OverallCond))
min(table(project$OverallCond))
barplot(table(project$OverallCond),col=rainbow(9),main="Overall condition",  xlab = "Overall condition Rating") 


#YearBuilt
round(stat.desc(project[,c("YearBuilt")]),0)
g <- ggplot(project,aes(YearBuilt))+ geom_histogram(color="White")
g <- g+ggtitle('Year Built')
g +  theme(legend.position="top", axis.text=element_text(size = 5))


#YearRemodAdd
round(stat.desc(project[,c("YearRemodAdd")]),0)
g <- ggplot(project,aes(YearRemodAdd))+ geom_histogram(color="White")
g <- g+ggtitle('Remodel date')
g +  theme(legend.position="top", axis.text=element_text(size = 5))


#RoofStyle
table(project$RoofStyle)
max(table(project$RoofStyle))
min(table(project$RoofStyle))
barplot(table(project$RoofStyle),col=rainbow(6),main="Roof Style",  xlab = "Roof Style") 


#RoofMatl
table(project$RoofMatl)
max(table(project$RoofMatl))
min(table(project$RoofMatl))
RoofM<- table(project$RoofMatl)
barplot(RoofM, names= names(RoofM),col=rainbow(8), las=2, main="Roof Material") 


#Exterior1st
table(project$Exterior1st)
max(table(project$Exterior1st))
min(table(project$Exterior1st))
Ext1<- table(project$Exterior1st)
barplot(Ext1, names= names(Ext1),col=rainbow(15), las=2, main="Exterior covering on house") 


#Exterior2nd
table(project$Exterior2nd)
max(table(project$Exterior2nd))
min(table(project$Exterior2nd))
Ext2<- table(project$Exterior2nd)
barplot(Ext2, names= names(Ext2),col=rainbow(16), las=2, main="Ext covering on house, more than one material") 

#MasVnrType
table(project$MasVnrType)
max(table(project$MasVnrType))
min(table(project$MasVnrType))
barplot(table(project$MasVnrType),col=rainbow(4),main="Masonry veneer type") 


#MasVnrArea
round(stat.desc(project[,c("MasVnrArea")]),0)
with(project, hist(MasVnrArea, breaks="FD", col="blue",  main = "Masonry veneer area ", xlab = "Masonry veneer area in square feet"))


#ExterQual
table(project$ExterQual)
max(table(project$ExterQual))
min(table(project$ExterQual))
barplot(table(project$ExterQual),col=rainbow(4),main="Exterior material quality") 


#ExterCond
table(project$ExterCond)
max(table(project$ExterCond))
min(table(project$ExterCond))
barplot(table(project$ExterCond),col=rainbow(5),main="Evaluates material on the exterior", xlab = "Material on the exterior") 



#Foundation
table(project$Foundation)
max(table(project$Foundation))
min(table(project$Foundation))
barplot(table(project$Foundation),col=rainbow(6),main="Type of foundation") 

#BsmtQual
table(project$BsmtQual)
max(table(project$BsmtQual))
min(table(project$BsmtQual))
barplot(table(project$BsmtQual),col=rainbow(4),main="Height of the basement") 


#BsmtCond
table(project$BsmtCond)
max(table(project$BsmtCond))
min(table(project$BsmtCond))
barplot(table(project$BsmtCond),col=rainbow(4),main="Basement Condition") 







