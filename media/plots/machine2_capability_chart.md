# Load required libraries
suppressPackageStartupMessages({
    library(tidyverse)
    library(ggplot2)
    library(plotly)
    library(htmlwidgets)
})

setwd("/content/project")
dir.create("media/plots", recursive = TRUE, showWarnings = FALSE)

# Filter the X007 dataset for Machine 2
filtered_data <- X007 %>% filter(Machine == 2 & Pressure == 200 & Temperature == 338)

# Calculate mean and standard deviation of PartLength
mean_pl <- mean(filtered_data$PartLength)
sd_pl <- sd(filtered_data$PartLength)

# Create a ggplot histogram with overlaid normal density curve
pc_chart_ggplot <- ggplot(filtered_data, aes(x = PartLength)) +
    geom_histogram(aes(y = after_stat(density)), binwidth = 0.5, fill = "#0072B2", color = "white", alpha = 0.7) +
    stat_function(fun = dnorm, args = list(mean = mean_pl, sd = sd_pl), color = "#D55E00", linewidth = 1) +
    labs(title = paste0("Process Capability Chart: PartLength (Machine 
2
, 
200
kPa, 
338
K)"),
         x = "PartLength",
         y = "Density") +
    theme_minimal() +
    theme(
        plot.title = element_text(size = 20, face = "bold"),
        axis.title.x = element_text(size = 18),
        axis.title.y = element_text(size = 18),
        axis.text.x = element_text(size = 14),
        axis.text.y = element_text(size = 14),
        panel.background = element_rect(fill = "white", colour = "white"),
        plot.background = element_rect(fill = "white", colour = "white")
    )
