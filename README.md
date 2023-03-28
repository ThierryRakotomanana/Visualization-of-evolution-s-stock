# Steps to create a data visualization with animint2

Here are the steps to create a data visualization with animint2 to compare the financial stock evolution of Apple Inc. (AAPL), Microsoft Corporation (MSFT), Tesla, Inc. (TSLA), and Amazon.com, Inc. (AMZN)

First, make sure the animint2 package is installed in your R environment. If not, install it using the following command:
```r
install.packages("animint2")
```
Next, import your data into R using the read.csv() function or any other appropriate function to load your data.

Once your data is loaded, use the animint() function to start creating your visualization. Here's an example code to create a data visualization to compare the stock evolution of AAPL, MSFT, TSLA, and AMZN:

```r
library(animint2)

data <- read.csv("your_file.csv")

p <- ggplot(data, aes(x = date, y = price, color = company)) +
  geom_line() +
  scale_color_manual(values = c("AAPL" = "red", "MSFT" = "blue", "TSLA" = "green", "AMZN" = "purple"))

anim <- animint(p, data = data, ggplot_build = TRUE)
```

In this example, we're using the ggplot2 library to create a line for each company. We're also using the scale_color_manual() function to set the colors of the lines for each company.

To view your data visualization, use the plot() function with your animint object:
```r
plot(anim)
```

Your data visualization will be opened in your default web browser. You can also save it locally using the saveHTML() function:
```r
saveHTML(anim, "filename.html")
```