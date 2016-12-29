#Change Log - Visuals API

The page contains a quick summary of the API versions.

Versions listed on this page are considered stable and should not change. For information about upcoming versions and features see the [Roadmap](roadmap/README.md)

##Utility libraries
* [Color Utils](https://github.com/Microsoft/powerbi-visuals-utils-colorutils)
* [Formatting Utils](https://github.com/Microsoft/powerbi-visuals-utils-formattingutils)
* [Dataview Utils](https://github.com/Microsoft/powerbi-visuals-utils-dataviewutils)
* [Type Utils](https://github.com/Microsoft/powerbi-visuals-utils-typeutils)
* [Interactivity Utils](https://github.com/Microsoft/powerbi-visuals-utils-interactivityutils)
* [SVG Utils](https://github.com/Microsoft/powerbi-visuals-utils-svgutils)
* [Tooltip Utils](https://github.com/Microsoft/powerbi-visuals-utils-tooltiputils)
* [Chart Utils](https://github.com/Microsoft/powerbi-visuals-utils-chartutils)
* [Test Utils](https://github.com/Microsoft/powerbi-visuals-utils-testutils)

##API Version 1.3.0
* **[tooltips](https://github.com/Microsoft/PowerBI-visuals/blob/master/Visual/Tooltips.md)** - support for tooltips

##API Version 1.2.0
* **colorPallette** - manage the colors used on your visual.
* **Multiple selection** - selectionManager can accept an array of `SelectionId`.
* **[R visuals](https://github.com/Microsoft/PowerBI-visuals/tree/master/RVisualTutorial)** - support for custom visuals using R scripts

##API Version 1.1.0

* Visual Host Addtions
    * **createSelectionIdBuilder** - allows for creation of unique identifiers used for data selection
    * **createSelectionManager** - manages the selection state of the visual and communicates changes to the visual host
    * **colors** - an array of default colors to use in your visual

##API Version v1.0.0

* Initial API release
