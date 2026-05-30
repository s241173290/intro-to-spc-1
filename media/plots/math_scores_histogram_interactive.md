
library(ggplot2)
library(plotly)
library(htmlwidgets)

p <- ggplot(bigclass, aes(x = Math)) +
  geom_histogram(binwidth = 50, fill = "#0072B2", color = "black") +
  labs(title = "Distribution of Math Scores", x = "Math Score", y = "Frequency") +
  theme_minimal() +
  theme(
    plot.title = element_text(size = 20, face = "bold", hjust = 0.5),
    axis.title.x = element_text(size = 18),
    axis.title.y = element_text(size = 18),
    axis.text.x = element_text(size = 14),
    axis.text.y = element_text(size = 14),
    panel.background = element_rect(fill = "white", colour = NA),
    plot.background = element_rect(fill = "white", colour = NA)
  )

interactive_plot <- ggplotly(p)

saveWidget(interactive_plot, "media/plots/math_scores_histogram_interactive.html", selfcontained = TRUE)

