---
title: "ggplot2_basics"
author: "Dev Paudel"
date: "June 8, 2016"
output: pdf_document
---

```{r setup, include=FALSE}
knitr::opts_chunk$set(echo = TRUE)
```

Learning ggplot2 basics:
ggplot2 works on the concept of layers so you can add one layer on top of the other.

Loading library
```{r}
library(ggplot2)
```

Basic plot: This just creates space where plots can be printed.
```{r}
#library(ggplot2)
ggplot(data=mpg, aes(x=displ, y=hwy))
```
\pagebreak

Now, we can add points on the template
```{r}
ggplot(data=mpg, aes(x=displ, y=hwy))+
  geom_point()
```
\pagebreak
 
Add linear fit line to the plot
```{r}
ggplot(data=mpg, aes(x=displ, y=hwy, colour=class))+
  geom_point() +
  geom_smooth(method="lm")
``` 
\pagebreak

Add aesthetic values and remove legend
```{r}
ggplot(data=mpg, aes(x=displ, y=hwy, colour=class))+
  geom_point() +
  geom_smooth(method="lm", se=FALSE)+
  theme(legend.position="none")
```  
\pagebreak

Put only single line
```{r}
ggplot(data=mpg, aes(x=displ, y=hwy))+
  geom_point(aes(colour=class)) +
  geom_smooth(method="lm", se=FALSE)+
  theme(legend.position="none")
```  

\pagebreak

Change colors
```{r}
ggplot(data=mpg, aes(x=displ, y=hwy))+
  geom_point(aes(colour=class)) +
  geom_smooth(method="lm", se=FALSE, colour="red")
```

\pagebreak

Some more examples
```{r}
ggplot(data=mpg, aes(x=displ, y=hwy))+
  geom_point(aes(colour=class)) +
  geom_smooth(method="lm", se=FALSE, colour="red")+
  xlab("Displacement")+
  ylab("Highway consumption")+
  ggtitle("Consumption vs displacement")
```

\pagebreak

```{r}
ggplot(data=mpg, aes(x=displ, y=hwy))+
  geom_point(aes(colour=class)) +
  geom_smooth(method="lm", se=FALSE, colour="red")+
  theme(legend.position="none")+
  xlab("Displacement")+
  ylab("Highway consumption")+
  ggtitle("Consumption vs displacement")
```

\pagebreak

```{r}
ggplot(data=mpg, aes(x=displ, y=hwy))+
  geom_point(aes(colour=class)) +
  geom_smooth(method="lm", se=FALSE, colour="red")+
  theme(legend.position="none")+
  xlab("Displacement")+
  ylab("Highway consumption")+
  ggtitle(quote(Consumption^2))
```

\pagebreak

```{r}
ggplot(data=mpg, aes(x=displ, y=hwy))+
  geom_point(aes(colour=class)) +
  geom_smooth(method="lm", se=FALSE, colour="red", linetype=2)+
  theme(legend.position="none")+
  xlab("Displacement")+
  ylab("Highway consumption")+
  ggtitle(quote(Consumption^2))
```

\pagebreak

```{r}
ggplot(data=mpg, aes(x=displ, y=hwy, colour=class))+
  geom_point() +
  geom_smooth(method="lm", se=FALSE, aes(linetype=class))+
  theme(legend.position="none")+
  xlab("Displacement")+
  ylab("Highway consumption")+
  ggtitle(quote(Consumption^2))
```

\pagebreak

```{r}
ggplot(data=mpg, aes(x=displ, y=hwy, colour=class))+
  geom_point() +
  geom_smooth(method="lm", se=FALSE, aes(linetype=class))+
  xlab("Displacement")+
  ylab("Highway consumption")+
  ggtitle(quote(Consumption^2))
```

\pagebreak

```{r}
ggplot(data=mpg, aes(x=displ, y=hwy, colour=class))+
  geom_point() +
  geom_smooth(method="lm", se=FALSE, aes(linetype=class))+
  xlab("Displacement")+
  ylab("Highway consumption")+
  ggtitle(quote(Consumption^2))+
  theme(line=element_line(linetype=3))
```

\pagebreak

```{r}
ggplot(data=mpg, aes(x=displ, y=hwy, colour=class))+
  geom_point() +
  geom_smooth(method="lm", se=FALSE, aes(linetype=class))+
  xlab("Displacement")+
  ylab("Highway consumption")+
  ggtitle(quote(Consumption^2))+
  scale_linetype_manual(values=rep(1,7))

```
