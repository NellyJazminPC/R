## Gráfico de ADMIXTURE

````
setwd("/home/n311/Escritorio/R_tarea/bin/")
#Library
library(tidyr)
library(dplyr)
library(ggplot2)
library(plyr)
#Data
tbl_cop_5=read.table(paste0("../data/admixture/copepodos_5.Q"))
full_cop<- read.delim("../copepodos.txt")
#Renombrar columnas
tbl_cop_5<-rename(tbl_cop_5, c("V1"="K1","V2"="K2","V3"="K3","V4"="K4","V5"="K5"))
#Cbind-merge
tbl_cbind_5<-cbind(tbl_cop_5, full_cop)




#Plot
par(mfrow=c(1,1),mar = c(1,1,2,1) + 0.9)
barplot(t(as.matrix(tbl_cbind_5[,1:5])), col=c("green", "blue", "red", "purple","yellow"),
        xlab=NA, ylab=NA, border=NA, xaxt="n", yaxt="n", cex.axis=0.8)

#Gather
tbl_gather_5 <- gather (tbl_cbind_5, key= K, value=admixture, K1:K5)
#Plot
admixture_5_cop <- ggplot(data=tbl_gather_5, aes(x=IND, y=admixture, fill=K)) + 
  geom_bar(stat="identity") + ylab("ADMIXTURE")+ xlab("INDIVIDUOS")+
  theme(axis.title.x = element_text(face="bold", size=10), 
        axis.title.y =element_blank(),
        axis.text.x  = element_text(angle=50, vjust=0.5, size=6, face = "bold")) +
  theme(legend.title= element_blank(),text = element_text(size=10))
#
admixture_5_cop

````