# Migrating to the Visuals API

To migrate from the legacy APIs to the new versioned Visuals API, use [PowerBI visuals CLI tools](https://github.com/Microsoft/PowerBI-visuals#setting-up-environment) and [NPM API packages](#utility-libraries-using-npm-packages).
Check the [Power BI visuals API roadmap](https://github.com/Microsoft/PowerBI-visuals/tree/master/Roadmap) for current and upcomming features.


## Utility libraries using NPM packages
The npm packages are intended to provide utility libraries for common functionlaity that is required by custom visuals, and to align it with Power BI's core visuals look & feel. 
Use the npm packages instead of the legacy APIs that were used in the past to achieve those common functionalities. Replace "Legacy Reference" in your code with the relevant "NPM package", as described below.

### TypeUtils

[TypeUtils](https://www.npmjs.com/package/powerbi-visuals-utils-typeutils) is a set of functions and classes to extend the basic types.

Legacy reference | NPM package namespace
--------------|----------------------
powerbi.Double | [powerbi.extensibility.utils.type.Double](https://github.com/Microsoft/powerbi-visuals-utils-typeutils/blob/master/docs/api/double.md)
powerbi.Prototype | [powerbi.extensibility.utils.type.Prototype](https://github.com/Microsoft/powerbi-visuals-utils-typeutils/blob/master/docs/api/prototype.md)
powerbi.visuals.jsCommon.PixelConverter | [powerbi.extensibility.utils.type.PixelConverter](https://github.com/Microsoft/powerbi-visuals-utils-typeutils/blob/master/docs/api/pixelconverter.md)

### SVGUtils

[SVGUtils](https://www.npmjs.com/package/powerbi-visuals-utils-svgutils) is a set of functions and classes to simplify SVG manipulations.

Legacy reference | NPM package namespace
--------------|----------------------
powerbi.visuals.jsCommon.CssConstants | [powerbi.extensibility.utils.svg.CssConstants](https://github.com/Microsoft/powerbi-visuals-utils-svgutils/blob/master/docs/api/cssConstants.md)
powerbi.visuals.SVGUtils methods | [powerbi.extensibility.utils.svg methods](https://github.com/Microsoft/powerbi-visuals-utils-svgutils/blob/master/docs/api/manipulatation.md)
powerbi.visuals.shapes.Rect | [powerbi.extensibility.utils.svg.shapes.Rect](https://github.com/Microsoft/powerbi-visuals-utils-svgutils/blob/master/docs/api/rect.md)
powerbi.visuals.getCoordinates | [powerbi.extensibility.utils.svg.getCoordinates](https://github.com/Microsoft/powerbi-visuals-utils-svgutils/blob/master/docs/api/pointer.md)

### DataViewUtils

[DataViewUtils](https://www.npmjs.com/package/powerbi-visuals-utils-dataviewutils) is a set of functions and classes to simplify parsing of the DataView object.

Legacy reference | NPM package namespace
--------------|----------------------
powerbi.data.DataRoleHelper | [powerbi.extensibility.utils.dataview.DataRoleHelper](https://github.com/Microsoft/powerbi-visuals-utils-dataviewutils/blob/master/docs/api/data-role-helper.md)
powerbi.DataViewObjects | [powerbi.extensibility.utils.dataview.DataViewObjects](https://github.com/Microsoft/powerbi-visuals-utils-dataviewutils/blob/master/docs/api/data-view-objects.md)
powerbi.DataViewObject  | [powerbi.extensibility.utils.dataview.DataViewObject](https://github.com/Microsoft/powerbi-visuals-utils-dataviewutils/blob/master/docs/api/data-view-object.md)
powerbi.visuals.converterHelper | [powerbi.extensibility.utils.dataview.converterHelper](https://github.com/Microsoft/powerbi-visuals-utils-dataviewutils/blob/master/docs/api/converter-helper.md)
none | [powerbi.extensibility.utils.dataview.DataViewObjectsParser](https://github.com/Microsoft/powerbi-visuals-utils-dataviewutils/blob/master/docs/api/data-view-objects-parser.md)

### FormattingUtils

[FormattingUtils](https://www.npmjs.com/package/powerbi-visuals-utils-formattingutils) is a set of functions and classes to format values.

Legacy reference | NPM package namespace
---------------------|----------------------
powerbi.TextMeasurementService | [powerbi.extensibility.utils.formatting.textMeasurementService](https://github.com/Microsoft/powerbi-visuals-utils-formattingutils/blob/master/docs/api/text-measurement-service.md)
powerbi.visuals.jsCommon.StringExtensions | [powerbi.extensibility.utils.formatting.stringExtensions](https://github.com/Microsoft/powerbi-visuals-utils-formattingutils/blob/master/docs/api/string-extensions.md)
powerbi.visuals.valueFormatter | [powerbi.extensibility.utils.formatting.valueFormatter](https://github.com/Microsoft/powerbi-visuals-utils-formattingutils/blob/master/docs/api/value-formatter.md)

### InteractivityUtils

[InteractivityUtils](https://www.npmjs.com/package/powerbi-visuals-utils-interactivityutils) is a set of functions and classes to simplify implementation of cross-selection and cross-filtering.

Legacy reference | NPM package namespace
--------------|----------------------
powerbi.visuals.InteractivityOptions | [powerbi.extensibility.utils.interactivity](https://github.com/Microsoft/powerbi-visuals-utils-interactivityutils/blob/master/docs/api/interactivityService.md)
powerbi.visuals.InteractivityUtils | [powerbi.extensibility.utils.interactivity.interactivityUtils](https://github.com/Microsoft/powerbi-visuals-utils-interactivityutils/blob/master/docs/api/interactivityUtils.md)


### TooltipUtils

[TooltipUtils](https://www.npmjs.com/package/powerbi-visuals-utils-tooltiputils) is a set of functions and classes to simplify usage of the Tooltip API.

Legacy reference | NPM package namespace
--------------|----------------------
powerbi.common.createTooltipService | [powerbi.extensibility.utils.tooltip.createTooltipServiceWrapper](https://github.com/Microsoft/powerbi-visuals-utils-tooltiputils/blob/master/docs/api/tooltipservice.md)
powerbi.common.ITooltipService | [powerbi.extensibility.utils.tooltip.ITooltipServiceWrapper](https://github.com/Microsoft/powerbi-visuals-utils-tooltiputils/blob/master/docs/api/tooltipservice.md#itooltipservicewrapper)
 

### ColorUtils

[ColorUtils](https://www.npmjs.com/package/powerbi-visuals-utils-colorutils) is a set of functions and classes to simplify color manipulations.

Legacy reference | NPM package namespace
--------------|----------------------
powerbi.visuals.ColorHelper | [powerbi.extensibility.utils.color.ColorHelper](https://github.com/Microsoft/powerbi-visuals-utils-colorutils/blob/master/docs/api/colorHelper.md)
powerbi.visuals.jsCommon.Color | [powerbi.extensibility.utils.color methods](https://github.com/Microsoft/powerbi-visuals-utils-colorutils/blob/master/docs/api/colorUtils.md)


### ChartUtils

[ChartUtils](https://www.npmjs.com/package/powerbi-visuals-utils-chartutils) is a set of interfaces to format chart properties, such as axes and data labels.

Legacy reference | NPM package namespace
--------------|----------------------
powerbi.visuals.AxisHelper methods | [powerbi.extensibility.utils.chart.axis methods](https://github.com/Microsoft/powerbi-visuals-utils-chartutils/blob/master/docs/api/axis-helper.md)
powerbi.DataLabelManager | [powerbi.extensibility.utils.chart.dataLabel.DataLabelManager](https://github.com/Microsoft/powerbi-visuals-utils-chartutils/blob/master/docs/api/data-label-manager.md)
powerbi.visuals.dataLabelUtils methods | [powerbi.extensibility.utils.chart.dataLabel.utils methods](https://github.com/Microsoft/powerbi-visuals-utils-chartutils/blob/master/docs/api/data-label-utils.md)


### TestUtils

[TestUtils](https://www.npmjs.com/package/powerbi-visuals-utils-testutils) is a set of mocks and functions to simplify unit testing.

Legacy reference | NPM package namespace
--------------|----------------------
none | [powerbi.extensibility.utils.test.mocks.MockIVisualHost](https://github.com/Microsoft/powerbi-visuals-utils-testutils/blob/master/docs/api/mock-ivisual-host.md)
none | [powerbi.extensibility.utils.test.mocks.createVisualHost](https://github.com/Microsoft/powerbi-visuals-utils-testutils/blob/master/docs/api/mock-ivisual-host.md#createvisualhost)
none | [powerbi.extensibility.utils.test.mocks.MockIColorPalette](https://github.com/Microsoft/powerbi-visuals-utils-testutils/blob/master/docs/api/mock-icolor-palette.md)
none | [powerbi.extensibility.utils.test.mocks.createColorPalette](https://github.com/Microsoft/powerbi-visuals-utils-testutils/blob/master/docs/api/mock-icolor-palette.md#createcolorpalette)
none | [powerbi.extensibility.utils.test.mocks.MockISelectionId](https://github.com/Microsoft/powerbi-visuals-utils-testutils/blob/master/docs/api/mock-iselectionid.md)
none | [powerbi.extensibility.utils.test.mocks.createSelectionId](https://github.com/Microsoft/powerbi-visuals-utils-testutils/blob/master/docs/api/mock-iselectionid.md#createselectionid)
none | [powerbi.extensibility.utils.test.mocks.MockISelectionIdBuilder](https://github.com/Microsoft/powerbi-visuals-utils-testutils/blob/master/docs/api/mock-iselection-idbuilder.md)
none | [powerbi.extensibility.utils.test.mocks.createSelectionIdBuilder](https://github.com/Microsoft/powerbi-visuals-utils-testutils/blob/master/docs/api/mock-iselection-idbuilder.md#createselectionidbuilder)
none | [powerbi.extensibility.utils.test.mocks.MockISelectionManager](https://github.com/Microsoft/powerbi-visuals-utils-testutils/blob/master/docs/api/mock-iselection-manager.md)
none | [powerbi.extensibility.utils.test.mocks.createSelectionManager](https://github.com/Microsoft/powerbi-visuals-utils-testutils/blob/master/docs/api/mock-iselection-manager.md#createselectionmanager)