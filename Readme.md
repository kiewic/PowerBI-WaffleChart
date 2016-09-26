> Note: this repository was recently moved from `powerbi-visuals-docs`.
>
> The old `powerbi-visuals` repository has been moved to [powerbi-visuals-core](https://github.com/Microsoft/PowerBI-visuals-core).


#Power BI Visuals

Learn how to build Power BI visuals!
 
##Developing Your First PowerBI Visual
 
This section is to provide you with a step by step tutorial of developing your first PowerBI visual.
In this tutorial, you will be building a simple bar chart. The source code is located here in the [Sample Bar Chart Repo](https://github.com/Microsoft/PowerBI-visuals-sampleBarChart).

![](Tutorial/images/SampleBarChart.png)

### Setting Up Environment
1. [Install PowerBI visuals CLI tool](tools/README.md#installation)
2. [Install SSL certifications to enable live preview of visuals](tools/CertificateSetup.md)
3. [Enable Developer Tools in PowerBI](tools/DebugVisualSetup.md)
4. [Create New PowerBI Visual Project](tools/usage.md#creating-a-new-visual)
5. [Start Development Server for Live Update and Incremental Development](tools/usage.md#testing-your-visual-in-powerbi)
6. [Adding the Debug Visual from the Visual Well into your Favorite Report](tools/usage.md#viewing-your-visual-in-powerbi)
7. [Adding External Libraries](Tutorial/ExternalLibraries.md)
8. [Installing Typings for Libraries](Tutorial/Typings.md)

### Building Bar Chart
1. [Building a Visual with Static Data](Tutorial/StaticVisual.md)
2. [Adding Databinding to the Bar Chart](Tutorial/DataBinding.md)
3. [Adding Color to the Bar Chart](Tutorial/ColorPalette.md)
4. [Adding Selection and Interaction with Other Visuals](Tutorial/Selection.md)
5. [Adding Static Objects to Property Pane](Tutorial/StaticObjects.md)
6. [Adding Databound Objects to Property Pane](Tutorial/DataBoundObjects.md)
7. [Finally Package for Distribution ... Done!](tools/usage.md#packaging-your-visual-for-distribution)

### Building R Custom Visual (corrplot)
1. [Creating a new R Custom Visual](RVisualTutorial/CreateNewVisual.md)
2. [Starting a simple R Script](RVisualTutorial/CorrplotScript.md)
3. [Adding a static property to the property pane](RVisualTutorial/PropertyPane.md)

##Table of Contents

* [Anatomy of a Visual Project](VisualProject.md)
* [Installing PowerBI Visuals Tool](tools/README.md#installation)
    * [Install SSL Certifications](tools/CertificateSetup.md)
    * [Enable Developer Tools](tools/DebugVisualSetup.md)
    * [Tools Usage Guide](tools/usage.md)
    * [Debugging Guide](tools/debugging.md)
* [Adding External Libraries](Tutorial/ExternalLibraries.md)
    * [Installing Typings for Libraries](Tutorial/Typings.md)
* [Visual Capabilities Definition](Capabilities/Capabilities.md)
    * [Data Roles](Capabilities/Capabilities.md#define-the-data-fields-your-visual-expects---dataroles)
    * [Data View Mappings](Capabilities/DataViewMappings.md)
    * [Objects](Capabilities/Objects.md)
    * [Highlighting](Capabilities/Highlighting.md)
* [Visual Documentation](Visual/Visual.md)
    * [Visual/IVisual Api](Visual/IVisualApi.md)
    * [Handling Selection in Visuals](Visual/Selection.md)
* [PowerBI Glossary](Glossary.md)
* [Change Log](ChangeLog.md)
* [Roadmap](Roadmap/README.md)

##Reporting Issues

If you have any issues with Power BI custom visuals or the command line tools please let us know. First, search the issues page to see if your issue has already been reported. If it already exists please contribute your experience to the comments otherwise create a new issue. Be sure to be as detailed as possible about exactly what you were doing when the issue occured and how we can reproduce it.

* [PowerBI-visuals-tools issue page](https://github.com/Microsoft/PowerBI-visuals-tools/issues) - Issues related to the CLI tools specifically
* [PowerBI-visuals issue page](https://github.com/Microsoft/PowerBI-visuals/issues) - Any other issues related to Power BI visuals
