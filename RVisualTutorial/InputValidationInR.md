# Input Validation in R Script
In order to write a truly robust R Powered Custom Visual, you should validate all the input you get before running some R function that expects specific values to be given.

For example, the corrplot function needs to run on at least two columns and at least two rows.
If the function gets one row, the function will fail.
`corrplot` also require that all column types will be numeric and non-constant

So you should prepare to validate your input prior to running the code.

## Example for input validation in R code

### Validate number of columns and rows
Here is an example for validating that we got the right columns types and at least two columns and at lease two rows:

 ```r
errorText <- NULL
#filter out non-numeric columns and constant columns
correctColumn <- function(someColumn) { is.numeric(someColumn) && length(unique(someColumn)) > 1 }
useColumns <- sapply(Values,correctColumn)
if(sum(useColumns) < ncol(Values))
  errorText <- "Filtered out non numeric columns and constant columns"

Values <- as.data.frame(Values[,useColumns])

columnCount <- ncol(Values)
rowCount <- nrow(Values)

if (rowCount < 2 || columnCount < 2) {
    plot.new()
    errorText<-paste(errorText, "Not enough input dimensions", sep="\n")
    title(main = NULL, sub = errorText, outer = FALSE, col.sub = "gray50", cex.sub = 0.75)
    quit()
}
```

In this example, if we get one row or one column, we will print some error message into the graphical device instead of leting the `corrplot` function to fail

### Validate column types


See [commit](https://github.com/Microsoft/PowerBI-visuals-sampleCorrPlotRVisual/commit/988057e9845ef24374b83ea0e15ae3c1f1873c90) for what was added at this step.