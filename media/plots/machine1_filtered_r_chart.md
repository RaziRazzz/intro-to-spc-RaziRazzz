# Load required libraries
suppressPackageStartupMessages({
    library(tidyverse)
    library(qcc)
    library(htmlwidgets)
})

# Filter the X007 dataset for Machine 1
filtered_data <- X007 %>% filter(Machine == 1 & Pressure == 200 & Temperature == 338)

# Prepare data for qcc (subgroups of 5)
xbar_data <- matrix(filtered_data$PartLength, ncol = 
5
, byrow = TRUE)

# Create the R-chart
r_chart_plot <- qcc(xbar_data, type = "R", nsigmas = 3,
                    title = "R Chart for PartLength (Machine 1, 200kPa, 338K)",
                    ylab = "Subgroup Range", xlab = "Subgroup Number")
