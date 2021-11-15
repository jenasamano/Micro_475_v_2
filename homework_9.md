Homework 9
================

``` r
library(shiny)
library(tidyverse)
```

    ## -- Attaching packages --------------------------------------- tidyverse 1.3.1 --

    ## v ggplot2 3.3.5     v purrr   0.3.4
    ## v tibble  3.1.4     v dplyr   1.0.7
    ## v tidyr   1.1.3     v stringr 1.4.0
    ## v readr   2.0.1     v forcats 0.5.1

    ## -- Conflicts ------------------------------------------ tidyverse_conflicts() --
    ## x dplyr::filter() masks stats::filter()
    ## x dplyr::lag()    masks stats::lag()

``` r
mpgData <- mtcars

# Starting a new app

# Define UI for miles per gallon app ----
ui <- fluidPage(
    
    passwordInput("password", "Password:"),
    actionButton("go","Go"),
    verbatimTextOutput("goodluck"),
    
    # App title ----
    titlePanel("Gas in the Car"),
    
    # Sidebar layout with input and output definitions ----
    sidebarLayout(
        
        # Sidebar panel for inputs ----
        sidebarPanel(
            
            # Input: Selector for variable to plot against mpg ----
            selectInput("variable", "Variable:",
                        c("Cylinders" = "cyl",
                          "Carborator" = "carb",
                          "Gears" = "gear")),
           
            # Input: Checkbox for whether outliers should be included ----
            checkboxInput("outliers", "Show outliers", FALSE)
            
        ),
        
        # Main panel for displaying outputs ----
        mainPanel(
            
            # Output: Formatted text for caption ----
            h3(textOutput("caption")),
            
            # Output: Plot of the requested variable against mpg ----
            plotOutput("mpgPlot")
            
        )
    )
)

# Define server logic to plot various variables against mpg ----
server <- function(input, output) {
    
    # Compute the formula text ----
    # This is in a reactive expression since it is shared by the
    # output$caption and output$mpgPlot functions
    formulaText <- reactive({
        paste("mpg ~", input$variable)
    })
    
    # Return the formula text for printing as a caption ----
    output$caption <- renderText({
        formulaText()
    })
    
    # Generate a plot of the requested variable against mpg ----
    # and only exclude outliers if requested
    output$mpgPlot <- renderPlot({
        boxplot(as.formula(formulaText()),
                data = mpgData,
                outline = input$outliers,
                col = "red", pch = 19)
    })
    
}


shinyApp(ui, server)
```

<div style="width: 100% ; height: 400px ; text-align: center; box-sizing: border-box; -moz-box-sizing: border-box; -webkit-box-sizing: border-box;" class="muted well">Shiny applications not supported in static R Markdown documents</div>
