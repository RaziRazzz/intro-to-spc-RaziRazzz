```R
# Load required libraries
suppressPackageStartupMessages(library(tidyverse))
suppressPackageStartupMessages(library(plotly))
suppressPackageStartupMessages(library(htmlwidgets))

# Data Preparation and Subgrouping
df_x007_filtered <- X007 %>%
  filter(Machine == 1 & Pressure == 200 & Temperature == 338)
n_subgroup <- 5
num_subgroups <- floor(nrow(df_x007_filtered) / n_subgroup)
df_x007_subgrouped_filtered <- df_x007_filtered[1:(num_subgroups * n_subgroup), ]
df_x007_subgrouped_filtered$subgroup <- rep(1:num_subgroups, each = n_subgroup)

# Calculate subgroup means
subgroup_data_filtered <- df_x007_subgrouped_filtered %>%
  group_by(subgroup) %>%
  summarise(
    x_bar = mean(PartLength),
    range = max(PartLength) - min(PartLength)
  )

# Overall Statistics
overall_x_bar_filtered <- mean(subgroup_data_filtered$x_bar)
avg_range_filtered <- mean(subgroup_data_filtered$range)

# Control Limits Constants for n=5
A2 <- 0.577

# X-bar Chart Limits
UCL_x_bar_filtered <- overall_x_bar_filtered + A2 * avg_range_filtered
LCL_x_bar_filtered <- overall_x_bar_filtered - A2 * avg_range_filtered

# Plot X-bar Chart
plot_x_bar_filtered <- ggplot(subgroup_data_filtered, aes(x = subgroup, y = x_bar)) +
  geom_line(color = "#0072B2") +
  geom_point(color = "#0072B2") +
  geom_hline(yintercept = overall_x_bar_filtered, linetype = "dashed", color = "black", linewidth=1) +
  geom_text(aes(x = max(subgroup), y = overall_x_bar_filtered, label = paste0("CL = ", round(overall_x_bar_filtered, 2))), 
            hjust = -0.1, vjust = -1, size = 5, color = "black") +
  geom_hline(yintercept = UCL_x_bar_filtered, linetype = "solid", color = "#D55E00", linewidth=1) +
  geom_text(aes(x = max(subgroup), y = UCL_x_bar_filtered, label = paste0("UCL = ", round(UCL_x_bar_filtered, 2))), 
            hjust = -0.1, vjust = -1, size = 5, color = "#D55E00") +
  geom_hline(yintercept = LCL_x_bar_filtered, linetype = "solid", color = "#D55E00", linewidth=1) +
  geom_text(aes(x = max(subgroup), y = LCL_x_bar_filtered, label = paste0("LCL = ", round(LCL_x_bar_filtered, 2))), 
            hjust = -0.1, vjust = 2, size = 5, color = "#D55E00") +
  labs(
    title = "X-bar Chart for PartLength (Machine 1, 200kPa, 338K)",
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

plotly_x_bar_filtered <- ggplotly(plot_x_bar_filtered)
# saveWidget(plotly_x_bar_filtered, output_x_bar_filtered_html_path, selfcontained = TRUE)
```
