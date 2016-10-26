# Building a new R Powered Custom Visual
In order to create a new R Powered Custom Visual we will run the following command:

```
pbiviz new sampleCorrPlotRVisual -t rvisual
```

This command will create a new folder stracture based on the template "rvisual"

This template includes a very basic ready to run R Visual which will actually run the following R script:

```
plot(Values)
```

This R script calls a generic function for plotting of R object. The data frame "Values" will contian columns in "Values" data role.

![Basic Plot Script Result](images/BasicPlot.png)

See [commit](https://github.com/Microsoft/PowerBI-visuals-sampleCorrPlotRVisual/commit/e7d31301bfa0ba9419e67383a9f27ae340e79fee) for what was added at this step.