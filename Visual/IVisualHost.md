# Visual Host
The host object contains a variety of objects and services that your visual can use. This documentation is a high level description of the services available.

## IVisualHost
IVisualHost currently contains these services and will be expanded in the upcoming api versions.
```typescript
export interface IVisualHost extends extensibility.IVisualHost {
    colors: IColorInfo[];
    createSelectionIdBuilder: () => visuals.ISelectionIdBuilder;
    createSelectionManager: () => ISelectionManager;
    allowInteractions: boolean;
}
```

### Colors
`colors: IColorInfo[]` - An array of default colors that your visual can use.

### Selection Builder
`createSelectionIdBuilder: () => visuals.ISelectionIdBuilder` - Generates and stores metadata for selectable items in your visual. [Learn more about Selection Builder](Selection.md#creating-selection-ids-selectionidbuilder)

### Selection Manager
`createSelectionManager: () => ISelectionManager` - The communication bridge used to notify the visual's host that there has been a change in the selection state. [Learn more about Selection Manager](Selection.md#managing-selection-selectionmanager)

### allowInteractions
`allowInteractions: boolean` - a boolean flag which hints whether or not the visual should be interactive. [Learn more about allowInteractions](AllowInteractions.md) 