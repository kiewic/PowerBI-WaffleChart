# Adding Color to your Visual 
Color is exposed as one of the services available on `IVisualHost`.

See [commit](https://github.com/Microsoft/PowerBI-visuals-sampleBarChart/commit/a521bc6b9930f630861dc08e27330030766ae057) for what was added at this step.

## Add Color to Data Points
Each data point will be represented by a different color. Add color to the BarChartDataPoint interface.

```typescript
/**
 * Interface for BarChart data points.
 *
 * @interface
 * @property {number} value    - Data value for point.
 * @property {string} category - Corresponding category of data value.
 * @property {string} color    - Color corresponding to data point.
 */
interface BarChartDataPoint {
    value: number;
    category: string;
    color: string;
};
```

## Color Palette
Color palette is a good abstraction for helping the visual pick a color for each data point.

**NOTE**: Color palette is not required, however it is a good way to manage your colors. Color palette can be used for your other visual projects.

See [commit](https://github.com/Microsoft/PowerBI-visuals-sampleBarChart/commit/a521bc6b9930f630861dc08e27330030766ae057) for color palette.

## Assigning Color to Data Points
We defined `visualTransform` as a construct to convert `dataView` to a view model Bar Chart can use.
Since we iterate through the data points in `visualTransform` it is also the ideal place to assign colors.

```typescript
let colorPalette: IColorPalette = createColorPalette(host.colors).reset();
for (let i = 0, len = Math.max(category.values.length, dataValue.values.length); i < len; i++) {
    barChartDataPoints.push({
        category: category.values[i],
        value: dataValue.values[i],
        color: colorPalette.getColor(category.values[i]).value,
    });
}
```