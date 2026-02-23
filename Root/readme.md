# Tutorial for root images data analysis

## Introduction 

Here we aim to evaluate the maize plant root elongation from root images.

All measured root shall have been stored in csv file with following format:
![](https://github.com/cndkczy/Tutorial/blob/main/Root/Screenshot.png)

In R make sure isntall Rmisc and ggplot:

    list.of.packages <- c("ggplot2", "Rmisc")
    new.packages <- list.of.packages[!(list.of.packages %in% installed.packages()[,"Package"])]
    if(length(new.packages)) install.packages(new.packages)

Using following codes to initial analysis:

    r25<-read.csv("[directory of your file]")
    r25$cmlength<-1.5*(r25$length/r25$ref) # transfer the length from pixels into cm
    r25<-subset(r25,!cmlength==0) #remove dead plants

    a1<-summarySE(r25,measurevar ="cmlength",groupvars = c("Geno","Date","Rep"),na.rm = TRUE ) # calcualte the mean
    ggplot(data=a1,aes(x=Geno,y=cmlength,fill=Rep,color=Rep))+geom_point()+facet_wrap("Date")+
      geom_errorbar(aes(ymin=cmlength-se,ymax=cmlength+se),width=.2,)+theme_bw()+
      theme(axis.text.x = element_text(angle = 45, hjust = 1,face = "bold.italic",size=10),        
        axis.text.y = element_text(face = "bold",size=10))

A figure like this shall be displayed:
![](https://github.com/cndkczy/Tutorial/blob/main/Root/Screenshot3.png)

Then visualize the root growth by date:

    ggplot(data=a1,aes(x=factor(Date,levels=c("5DAP","7DAP","12DAP")),y=cmlength,group=Geno,fill=Rep,color=Rep))+geom_point()+
      geom_errorbar(aes(ymin=cmlength-se,ymax=cmlength+se),width=.2)+
      geom_line(aes(group=Rep,fill=Rep,color=Rep))+
      geom_line(data=a1[1:3,2:9],size=1,linetype = "dotdash",color="red",aes(x=factor(Date,levels=c("5DAP","7DAP","12DAP")),y=cmlength,group=g2))+
      geom_errorbar(data=a1[1:3,2:9],width=0.2,color="red",aes(x=factor(Date,levels=c("5DAP","7DAP","12DAP")),ymin=cmlength-se,ymax=cmlength+se,group=g2))+
      facet_wrap(~Geno)+
      theme_bw()+
      theme(axis.text.x = element_text(angle = 45, hjust = 1,face = "bold.italic",size=10),        
            axis.text.y = element_text(face = "bold",size=10))
Above codes shall make a figure display time-lapse root growth:
![](https://github.com/cndkczy/Tutorial/blob/main/Root/Screenshot2.png)
