We are happy to announce that Power BI Custom Visuals API has now been upgraded to v1.3.

With change of API we updated the [development environment](https://github.com/Microsoft/PowerBI-visuals#setting-up-environment). PowerBI visuals CLI tools bring next level of degugging and development to your visual with its [project generator](https://github.com/Microsoft/PowerBI-visuals/blob/master/tools/usage.md#creating-a-new-visual) and [livereload feature](https://github.com/Microsoft/PowerBI-visuals/blob/master/tools/usage.md#testing-your-visual-in-powerbi)

To migrate to the new API you can easily use [PowerBI visuals CLI tools](https://github.com/Microsoft/PowerBI-visuals#setting-up-environment) and [new NPM API packages](/Microsoft/PowerBI-visuals/blob/master/Tutorial/MigrationGuidlineAPI.1.3.md#typeutils). Check PowerBi roadmap document with current and upcomming feature https://github.com/Microsoft/PowerBI-visuals/tree/master/Roadmap. Power BI Custom Visuals API v1 will reach the end of the half-year deprecation window on 1 February, 2017 (TODO check date). If you've already upgraded your code to call API v1.3, your visual shouldn't be affected by these changes. 

The list of npm packages you could use instead of deprecated core Classes and Interfaces (check linked install and usage document):

## TypeUtils

[TypeUtils](https://www.npmjs.com/package/powerbi-visuals-utils-typeutils) is a set of functions and classes in order to extend the basic types for Power BI custom visuals.

Deprecated Reference | NPM package namespace
--------------|----------------------
powerbi.Double | [powerbi.extensibility.utils.type.Double](https://github.com/Microsoft/powerbi-visuals-utils-typeutils/blob/master/docs/api/double.md)
powerbi.Prototype | [powerbi.extensibility.utils.type.Prototype](https://github.com/Microsoft/powerbi-visuals-utils-typeutils/blob/master/docs/api/prototype.md)
powerbi.visuals.jsCommon.PixelConverter | [powerbi.extensibility.utils.type.PixelConverter](https://github.com/Microsoft/powerbi-visuals-utils-typeutils/blob/master/docs/api/pixelconverter.md)


## SVGUtils

[SVGUtils](https://www.npmjs.com/package/powerbi-visuals-utils-svgutils) is a set of functions and classes in order to simplify SVG manipulations for Power BI custom visuals.

Deprecated Reference | NPM package namespace
--------------|----------------------
powerbi.visuals.jsCommon.CssConstants | [powerbi.extensibility.utils.svg.CssConstants](https://github.com/Microsoft/powerbi-visuals-utils-svgutils/blob/master/docs/api/cssConstants.md)
powerbi.visuals.SVGUtils methods | [powerbi.extensibility.utils.svg methods](https://github.com/Microsoft/powerbi-visuals-utils-svgutils/blob/master/docs/api/manipulatation.md)
powerbi.visuals.shapes.Rect | [powerbi.extensibility.utils.svg.shapes.Rect](https://github.com/Microsoft/powerbi-visuals-utils-svgutils/blob/master/docs/api/rect.md)
powerbi.visuals.getCoordinates | [powerbi.extensibility.utils.svg.getCoordinates](https://github.com/Microsoft/powerbi-visuals-utils-svgutils/blob/master/docs/api/pointer.md)


## DataViewUtils

[DataViewUtils](https://www.npmjs.com/package/powerbi-visuals-utils-dataviewutils) is a set of functions and classes in order to simplify parsing of the DataView object for Power BI custom visuals.

Deprecated Reference | NPM package namespace
--------------|----------------------
powerbi.data.DataRoleHelper | [powerbi.extensibility.utils.dataview.DataRoleHelper](https://github.com/Microsoft/powerbi-visuals-utils-dataviewutils/blob/master/docs/api/data-role-helper.md)
powerbi.DataViewObjects | [powerbi.extensibility.utils.dataview.DataViewObjects](https://github.com/Microsoft/powerbi-visuals-utils-dataviewutils/blob/master/docs/api/data-view-objects.md)
powerbi.DataViewObject  | [powerbi.extensibility.utils.dataview.DataViewObject](https://github.com/Microsoft/powerbi-visuals-utils-dataviewutils/blob/master/docs/api/data-view-object.md)
powerbi.visuals.converterHelper | [powerbi.extensibility.utils.dataview.converterHelper](https://github.com/Microsoft/powerbi-visuals-utils-dataviewutils/blob/master/docs/api/converter-helper.md)
none | [powerbi.extensibility.utils.dataview.DataViewObjectsParser](https://github.com/Microsoft/powerbi-visuals-utils-dataviewutils/blob/master/docs/api/data-view-objects-parser.md)


## FormattingUtils

[FormattingUtils](https://www.npmjs.com/package/powerbi-visuals-utils-formattingutils) is a set of functions and classes in order to format values for Power BI custom visuals.

Deprecated Reference | NPM package namespace
---------------------|----------------------
powerbi.TextMeasurementService | [powerbi.extensibility.utils.formatting.textMeasurementService](https://github.com/Microsoft/powerbi-visuals-utils-formattingutils/blob/master/docs/api/text-measurement-service.md)
powerbi.visuals.jsCommon.StringExtensions | [powerbi.extensibility.utils.formatting.stringExtensions](https://github.com/Microsoft/powerbi-visuals-utils-formattingutils/blob/master/docs/api/string-extensions.md)
powerbi.visuals.valueFormatter | [powerbi.extensibility.utils.formatting.valueFormatter](https://github.com/Microsoft/powerbi-visuals-utils-formattingutils/blob/master/docs/api/value-formatter.md)


## InteractivityUtils

[InteractivityUtils](https://www.npmjs.com/package/powerbi-visuals-utils-interactivityutils) is a set of functions and classes in order to simplify implementation of cross-selection and cross-filtering for Power BI custom visuals.

Deprecated Reference | NPM package namespace
--------------|----------------------
powerbi.visuals.InteractivityOptions | [powerbi.extensibility.utils.interactivity](https://github.com/Microsoft/powerbi-visuals-utils-interactivityutils/blob/master/docs/api/interactivityService.md)
powerbi.visuals.InteractivityUtils | [powerbi.extensibility.utils.interactivity.interactivityUtils](https://github.com/Microsoft/powerbi-visuals-utils-interactivityutils/blob/master/docs/api/interactivityUtils.md)


## TooltipUtils

[TooltipUtils](https://www.npmjs.com/package/powerbi-visuals-utils-tooltiputils) is a set of functions and classes in order to simplify usage of the Tooltip API for Power BI custom visuals.

Deprecated Reference | NPM package namespace
--------------|----------------------
powerbi.common.createTooltipService | [powerbi.extensibility.utils.tooltip.createTooltipServiceWrapper](https://github.com/Microsoft/powerbi-visuals-utils-tooltiputils/blob/master/docs/api/tooltipservice.md)
powerbi.common.ITooltipService | [powerbi.extensibility.utils.tooltip.ITooltipServiceWrapper](https://github.com/Microsoft/powerbi-visuals-utils-tooltiputils/blob/master/docs/api/tooltipservice.md#itooltipservicewrapper)
 

## ColorUtils

[ColorUtils](https://www.npmjs.com/package/powerbi-visuals-utils-colorutils) is a set of functions and classes in order to simplify color manipulations for Power BI custom visuals.

Deprecated Reference | NPM package namespace
--------------|----------------------
powerbi.visuals.ColorHelper | [powerbi.extensibility.utils.color.ColorHelper](https://github.com/Microsoft/powerbi-visuals-utils-colorutils/blob/master/docs/api/colorHelper.md)
powerbi.visuals.jsCommon.Color | [powerbi.extensibility.utils.color methods](https://github.com/Microsoft/powerbi-visuals-utils-colorutils/blob/master/docs/api/colorUtils.md)


## ChartUtils

[ChartUtils](https://www.npmjs.com/package/powerbi-visuals-utils-chartutils) is a set of interfaces for creating powerbi custom visuals.

Deprecated Reference | NPM package namespace
--------------|----------------------
powerbi.visuals.AxisHelper methods | [powerbi.extensibility.utils.chart.axis methods](https://github.com/Microsoft/powerbi-visuals-utils-chartutils/blob/master/docs/api/axis-helper.md)
powerbi.DataLabelManager | [powerbi.extensibility.utils.chart.dataLabel.DataLabelManager](https://github.com/Microsoft/powerbi-visuals-utils-chartutils/blob/master/docs/api/data-label-manager.md)
powerbi.visuals.dataLabelUtils methods | [powerbi.extensibility.utils.chart.dataLabel.utils methods](https://github.com/Microsoft/powerbi-visuals-utils-chartutils/blob/master/docs/api/data-label-utils.md)


## TestUtils

[TestUtils](https://www.npmjs.com/package/powerbi-visuals-utils-testutils) is a set of mocks and fakes in order to simplify unit testing for Power BI custom visuals. 100% new library could help you in creation of unit tests.

Deprecated Reference | NPM package namespace
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

