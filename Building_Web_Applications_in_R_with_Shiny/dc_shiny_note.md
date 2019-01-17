Github Repo: https://github.com/enliktjioe/datacamp

## Chapter 1 - Introduction and Shiny basics
**Tips**
* Always run the entire script, not just up to the point where you’re developing code
* Sometimes the best way to see what’s wrong is to run the app and review the error
* Watch out for commas!

## Anatomy of a Shiny app
```R
library(shiny)

## User Interface - controls the layout and appearance of app
ui <- fluidPage()

## Server functio - contains instructions needed to build app
server <- function(input, output) {}


## shinyApp() - Creates the Shiny app object
shinyApp(ui = ui, server = server)
```

## Data
Simple movie browser app
movies.Rdata
Data from IMDB and Rotten Tomatoes on random samples

