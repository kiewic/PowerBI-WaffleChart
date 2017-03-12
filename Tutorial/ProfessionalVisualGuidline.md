# Developer guide: How to build a Power BI custom visual

## Requirements of a quality grade custom visual

Power BI users expect the visuals to contain a minimum set of features and work properly in their Power BI environment. A full-featured visual should include features like formatting, selection and filtering, exception handling, and responsiveness.

Check out the sample Bar Chart [tutorial](https://github.com/Microsoft/PowerBI-visuals#building-bar-chart) as an example of quality grade for a Power BI custom visual.

![](images/SampleBarChart.png)

## Dataset validation

Make sure you include dataset validations in your custom visual, for various data types.

1. Support for large data sets
2. Provide validation for all data types in the Field well (expect any type of data)
3. Provide error handling for unexpected data values

The [DataViewUtils](https://www.npmjs.com/package/powerbi-visuals-utils-dataviewutils) NPM package can help you with reaching those three.

## Formatting options

Support a wide variety of formatting options.

Add this list of expected Formating Panel options, which let users to specify "look and feel" of the visual:

1. Data labels properties:
  - Color
  - Font size
  - Label style
  - Display unit
  - Decimal places
  - Density
  - Position

2. Legend properties:
  - Font size
  - Color
  - Title
  - Position
  
3. Axis (X-Axis, Y-Axis, or both) properties:
  - Title
  - Color
  - Display unit

4. Data points properties:
  - Font size
  - Fill
  - Tooltips
  - Sort

These options are declared in the [Capabilities](https://github.com/Microsoft/PowerBI-visuals/blob/master/Capabilities/Capabilities.md) file of the visual.

For parsing and validataion, use [DataViewObjectsParser](https://github.com/Microsoft/powerbi-visuals-utils-dataviewutils/blob/master/docs/api/data-view-objects-parser.md) from the [DataViewUtils](https://www.npmjs.com/package/powerbi-visuals-utils-dataviewutils) NPM package.

Use the Power BI [Color Palette](https://github.com/Microsoft/PowerBI-visuals/blob/master/Tutorial/ColorPalette.md) for all color properties.

## Support cross-filtering when available

Provide cross-filtering or cross-highlighting, if appropriate, for your visual. Cross-filtering is when selecting elements in one visual filters the other visuals in the report and vice-versa. Cross-highlighting is when selecting an element in a visual highlights other visuals and vice-versa.

This gives a better presentation integration with any report and helps users to use your visual as selection control for their data in the report.

Learn more about [visual selection](https://github.com/Microsoft/PowerBI-visuals/blob/master/Visual/Selection.md) functionality. You can also review the [selection example](https://github.com/Microsoft/PowerBI-visuals/blob/master/Tutorial/Selection.md).

## Versioning

Set the version of your visual.

Versioning has the following format: `xx.yy.zz`. "xx" is the major version, "yy" is the minor version, "zz" is a patch/hotfix.

**MAJOR.MINOR.PATCH**

**MAJOR** version is incremented when you make incompatible API changes.

1. changes that are done after incompatible changes in infrastructure code or

2. changes that require a user to update their report that contains this visual because the visual does not support previous versions of the settings.

**MINOR** version is updated when you add functionality/feature that is backwards-compatible.

**PATCH** (or HOTFIX) version is updated when you make backwards-compatible bug fixes.

Every package submission must have a unique version, incremental to the previous one.

## Testing

Make sure you test your visual well on all major browsers and all Power BI endpoints: PowerBI.com, Power BI Desktop, Power BI mobile apps (iPad, iPhone, Android phone, Android Tablet, Windows Universal app, Windows phone)

Upon receipt of your visual submission, the Power BI custom visual team will use the following test cases and acceptance criteria to validate your submission.

Use the [TestUtils](https://www.npmjs.com/package/powerbi-visuals-utils-testutils) NPM package. It can help you with creation of unit tests.

### Best practices

Use the following guidelines while planning your visual:

1. The behavior of your visual should be the same on mobile, web and desktop versions of Power BI application. And, mobile-friendly at the same time in terms of touch support and tooltip appearance.

2. Test with various types of data and datasets. Do not rely only on your sample dataset that was used for development of the custom visual.

3. Test critical paths! Have multiple instances of the visual on the same page or the same report, big datasets, different types of data, user input and formatting settings, etc.

4. Ensure that elements in the visual do not overlap each other on different sizes of the visual, different types of datasets and different formatting settings.

5. Use [Segoe UI](https://www.microsoft.com/typography/fonts/family.aspx?FID=331) font for user interface text. This way labels of your visual will be the same style as other visuals on the report. Example of such font fallback:
        
        .chicletSlicer {
            font-family: 'Segoe UI', 'wf_segoe-ui_normal', helvetica, arial, sans-serif;
        }

6. Set min/max fields for data roles to limit the number of fields that can be dropped into the specific field bucket.

7. Add unit tests that will validate your visual ensuring that new changes will not break your visual.

Be sure to review [Common problems of custom visuals](./SubmissionCommonProblems.md). Also, check our [test cases and acceptable web browsers](./SubmissionTesting.md).
