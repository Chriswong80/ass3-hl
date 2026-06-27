
library(ggplot2)
library(plotly)

p <- ggplot(machine1_data, aes(x = Pressure, y = PartResistance, fill = Temperature)) +
  geom_boxplot() +
  labs(
    title = 'Part Resistance by Pressure and Temperature (Machine 1)',
    x = 'Pressure (psi)',
    y = 'Part Resistance (Ohms)',
    fill = 'Temperature (°C)'
  ) +
  theme_minimal() +
  theme(
    plot.title = element_text(size = 18, face = "bold"),
    axis.title.x = element_text(size = 18),
    axis.title.y = element_text(size = 18),
    axis.text.x = element_text(size = 14),
    axis.text.y = element_text(size = 14),
    legend.title = element_text(size = 16),
    legend.text = element_text(size = 14)
  ) +
  geom_hline(yintercept = 10, linetype = "dashed", color = "red", size = 1, alpha = 0.7) # USL for resistance

print(p)

