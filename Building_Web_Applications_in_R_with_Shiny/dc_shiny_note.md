Github Repo: https://github.com/enliktjioe/datacamp

# Chapter 1 - Introduction and Shiny basics
**Tips**
* Always run the entire script, not just up to the point where you’re developing code
* Sometimes the best way to see what’s wrong is to run the app and review the error
* Watch out for commas!

## Anatomy of a Shiny app
```R
library(shiny)

## User Interface - controls the layout and appearance of app
ui <- fluidPage()

## Server function - contains instructions needed to build app
server <- function(input, output) {}


## shinyApp() - Creates the Shiny app object
shinyApp(ui = ui, server = server)
```

## Data
* Simple movie browser app
* movies.Rdata
* Data from IMDB and Rotten Tomatoes on random samples


## Server function
```R
server <- function(input, output) {

	# Create the scatterplot object the plotOutput function is expecting
	output$scatterplot <- renderPlot({
			# Good ol' ggplot2 code, with inputs from UI
			ggplot(data = movies, aes_string(x = input$x, y = input$y)) +
			geom_point()

		})
}
```

### Rules of server functions
1. Save objects to display to `output$xx`
2. Build objects to display with `render*()`
3. Use input values with `input$xx`


## RECAP
* UI built by HTML, CSS, JS
* Shiny don't require you to learn HTML, CSS, JS
* R Server instructions

<br />
<br />

# Chapter 2 - Inputs, outputs, and rendering functions

## checkboxInput
1. **ui**: Add an input widget that the user can intercact with to check/uncheck the box
2. **ui**: Add an output defining wehere the data table should appear
3. **server**: Add a reactive expression that creates the data table *if* the checkbox is checked.

 
