# R-plot-in-Power-BI
Embed R plots into Power BI. This post demonstrates how to connect R with Power BI and write R scripts in the shell to execute them.
The reason for this is that if I want to display beautiful R plots, such as ggplot visualizations, in Power BI, I must use R visuals within Power BI.

In R script in Power BI, i have to write a complet R codes in RStudio then copy and paste in Power BI ro run them.
EX: 
### R script in R script editor:

library(ggplot2)
library(readr)

hosbeds <- read_csv("E:/Statistics/PowerBI/Data/hospital_beds_USA_v1.csv")

ggplot(data = hosbeds) +
  geom_boxplot(mapping = aes(x = type, y = beds, fill = type, color = type), 
               alpha = 0.6, width = 0.6, outlier.color = "red", outlier.shape = 16) +  
  scale_fill_brewer(palette = "Set2") +  
  scale_color_brewer(palette = "Dark2") + 
  theme_minimal() +  
  labs(title = "Distribution of Beds by Type",
       x = "Hospital Type",
       y = "Number of Beds") +  
  theme(plot.title = element_text(hjust = 0.5, face = "bold", size = 14)) 

