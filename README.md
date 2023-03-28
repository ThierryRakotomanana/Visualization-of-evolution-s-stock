install.packages("animint2")

library(animint2)

data <- read.csv("votre_fichier.csv")

p <- ggplot(data, aes(x = date, y = prix, color = entreprise)) +
  geom_line() +
  scale_color_manual(values = c("AAPL" = "red", "MSFT" = "blue", "TSLA" = "green", "AMZN" = "purple"))

anim <- animint(p, data = data, ggplot_build = TRUE)

plot(anim)

saveHTML(anim, "nom_de_fichier.html")