# Building a new R Custom Visual
In order to start a new R Custom Visual we will run the following command:

```
pbiviz new sampleCorrPlotRVisual -t rvisual --api-version 1.2.0
```

This command will create a new folder stracture based on the template "rvisual"

This template includes a very basic ready to run R Visual which will actually run the following R script:

```
plot(Values)
```

This script will generate a very basic plot of whatever the user will drag to the Values data role

![Basic Plot Script Result](images/BasicPlot.png)

See [commit](https://github.com/Microsoft/PowerBI-visuals-sampleCorrPlotRVisual/commit/e7d31301bfa0ba9419e67383a9f27ae340e79fee) for what was added at this step.