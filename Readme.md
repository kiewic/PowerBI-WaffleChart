#Power BI Visuals Documentation

Learn how to build Power BI visuals. We're still working on these docs, but they should be ready by 8/2/2016.
 
##Developing Your First PowerBI Visual
 
This section is to provide you with a step by step tutorial of developing your first PowerBI visual.
In this tutorial, you will be building a simple bar chart. The source code is located here. [Sample Bar Chart Repo](https://github.com/Microsoft/PowerBI-visuals-sampleBarChart)

![](Tutorial/images/SampleBarChart.png)

1. Install PowerBI visuals CLI tool. [Installing PowerBI Visuals Tool](tools/README.md#installation)
2. Install certifications to enable live preview of visuals. [Install SSL Certifications](tools/CertificateSetup.md)
3. Enable developer tools in PowerBI. [Enable Developer Tools](tools/DebugVisualSetup.md)
4. Create new PowerBI visual project. [Creating a New Visual](tools/usage.md#creating-a-new-visual)
5. Start development server for live update and incremental development. [Start Development Server](tools/usage.md#testing-your-visual-in-powerbi)
6. Add the debug visual from your visual well into your favorite report. [Viewing your Visual](tools/usage.md#viewing-your-visual-in-powerbi)
7. Adding external libraries. [Adding External Libraries](Tutorial/ExternalLibraries.md)
8. Install typings for libraries. [Installing Typings for Libraries](Tutorial/Typings.md)
9. Build a visual with static data. [Building a Visual with Static Data](Tutorial/StaticVisual.md)
10. Add Databinding to your Visual. [Adding Databinding to your Visual](Tutorial/DataBinding.md)

![](http://www.animatedgif.net/underconstruction/5consbar2_e0.gif)
##Table of Contents

* [Anatomy of a Visual Project](VisualProject.md)
* [Installing PowerBI Visuals Tool](tools/README.md#installation)
    * [Install SSL Certifications](tools/CertificateSetup.md)
    * [Enable Developer Tools](tools/DebugVisualSetup.md)
    * [Tools Usage Guide](tools/usage.md)
* [Adding External Libraries](Tutorial/ExternalLibraries.md)
    * [Installing Typings for Libraries](Tutorial/Typings.md)
* [Visual Capabilities Definition](Capabilities/Capabilities.md)
    * [Data Roles](Capabilities/Capabilities.md#define-the-data-fields-your-visual-expects---dataroles)
    * [Data View Mappings](Capabilities/DataViewMappings.md)
    * [Objects](Capabilities/Objects.md)
* [Visual Documentation](Visual/Visual.md)
    * [Visual/IVisual Api](Visual/IVisualApi.md)
    * [Handling Selection in Visuals](Visual/Selection.md)
* [PowerBI Glossary](Glossary.md)
* [Change Log](ChangeLog.md)
* [Roadmap](Roadmap/README.md)
