```R
# Load required libraries
suppressPackageStartupMessages(library(tidyverse))
suppressPackageStartupMessages(library(plotly))
suppressPackageStartupMessages(library(htmlwidgets))

# Generate the histogram
p <- ggplot(bigclass, aes(x = Math)) +
  geom_histogram(binwidth = 25, fill = "#0072B2", color = "white") +
  labs(
    title = "Distribution of Math Scores",
    x = "Math Score",
    y = "Frequency"
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

# Convert to plotly object for interactivity
plotly_p <- ggplotly(p)

# Save the plot as an HTML widget
# saveWidget(plotly_p, output_html_path, selfcontained = TRUE)
```
