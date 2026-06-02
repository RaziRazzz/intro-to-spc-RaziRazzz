```R
# Load required libraries
suppressPackageStartupMessages(library(tidyverse))
suppressPackageStartupMessages(library(plotly))
suppressPackageStartupMessages(library(htmlwidgets))

# Data Preparation and Subgrouping
df_x007 <- X007
n_subgroup <- 5
num_subgroups <- floor(nrow(df_x007) / n_subgroup)
df_x007_subgrouped <- df_x007[1:(num_subgroups * n_subgroup), ]
df_x007_subgrouped$subgroup <- rep(1:num_subgroups, each = n_subgroup)

# Calculate subgroup means and ranges
subgroup_data <- df_x007_subgrouped %>%
  group_by(subgroup) %>%
  summarise(
    x_bar = mean(PartLength),
    range = max(PartLength) - min(PartLength)
  )

# Overall Statistics
overall_x_bar <- mean(subgroup_data$x_bar)
avg_range <- mean(subgroup_data$range)

# Control Limits Constants for n=5
A2 <- 0.577
D3 <- 0
D4 <- 2.114

# X-bar Chart Limits
UCL_x_bar <- overall_x_bar + A2 * avg_range
LCL_x_bar <- overall_x_bar - A2 * avg_range

# Plot X-bar Chart
plot_x_bar <- ggplot(subgroup_data, aes(x = subgroup, y = x_bar)) +
  geom_line(color = "#0072B2") +
  geom_point(color = "#0072B2") +
  geom_hline(yintercept = overall_x_bar, linetype = "dashed", color = "black", linewidth=1) +
  geom_text(aes(x = max(subgroup), y = overall_x_bar, label = paste0("CL = ", round(overall_x_bar, 2))), 
            hjust = -0.1, vjust = -1, size = 5, color = "black") +
  geom_hline(yintercept = UCL_x_bar, linetype = "solid", color = "#D55E00", linewidth=1) +
  geom_text(aes(x = max(subgroup), y = UCL_x_bar, label = paste0("UCL = ", round(UCL_x_bar, 2))), 
            hjust = -0.1, vjust = -1, size = 5, color = "#D55E00") +
  geom_hline(yintercept = LCL_x_bar, linetype = "solid", color = "#D55E00", linewidth=1) +
  geom_text(aes(x = max(subgroup), y = LCL_x_bar, label = paste0("LCL = ", round(LCL_x_bar, 2))), 
            hjust = -0.1, vjust = 2, size = 5, color = "#D55E00") +
  labs(
    title = "X-bar Chart for PartLength",
    x = "Subgroup Number",
    y = "Subgroup Mean (PartLength)"
  ) +
  theme_minimal() +
  theme(
    plot.title = element_text(size = 20, face = "bold"),
    axis.title.x = element_text(size = 18),
    axis.title.y = element_text(size = 18),
    axis.text.x = element_text(size = 14),
    axis.text.y = element_text(size = 14),
    panel.background = element_rect(fill = "white", colour = "white")
  )

plotly_x_bar <- ggplotly(plot_x_bar)
# saveWidget(plotly_x_bar, output_x_bar_html_path, selfcontained = TRUE)
```
