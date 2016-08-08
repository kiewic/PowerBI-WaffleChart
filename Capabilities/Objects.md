#Objects

Objects describe customizable properties associated with the visual.
Each object can have multiple properties and each property has a type associated with it.
Types refer to what the property will be. See below for more information about types.

`myCustomObject` is the internal name used to reference the object within `dataView` and `enumerateObjectInstances`

```json
"objects": {
    "myCustomObject": {
        "displayName": "My Object Name",
        "properties": { ... }
    }
}
```

## Display Name
`displayName` is the name that will be shown in the property pane.

## Properties
`properties` is a map of properties defined by the developer.

```json
"properties": {
    "myFirstProperty": {
        "displayName": "firstPropertyName",
        "type": ValueTypeDescriptor | StructuralTypeDescriptor
    }
}
```

**NOTE**: `show` is a special property that enables a switch to toggle the object.

Example:

```json
"properties": {
    "show": {
        "displayName": "My Property Switch",
        "type": {"bool": true}
    }
}
```

### Property Types

There are 2 types of property types: `ValueTypeDescriptor` and `StructuralTypeDescriptor`.

#### Value Type Descriptor
`ValueTypeDescriptor` are mostly primitive types and are typically used as a static object.
Here are some of the common `ValueTypeDescriptor`

```typescript
export interface ValueTypeDescriptor {
    text?: boolean;
    numeric?: boolean;
    integer?: boolean;
    bool?: boolean;
}
```

#### Structural Type Descriptor
`StructuralTypeDescriptor` are mostly used for data bound objects.
Fill is the most common `StructuralTypeDescriptor`

```typescript
export interface StructuralTypeDescriptor {
    fill?: FillTypeDescriptor;
}
```

#enumerateObjectInstances
To use objects effectively you will need a function in your custom visual called `enumerateObjectInstances`. This function will populate the propery pane with objects and will also determine where your objects should be bound within the dataView.  

Here is what a typical setup looks like:
```typescript
public enumerateObjectInstances(options: EnumerateVisualObjectInstancesOptions): VisualObjectInstanceEnumeration{
    let objectName = options.objectName;
    let objectEnumeration = VisualObjectInstance[] = [];

    switch( objectName ){
        case 'myCustomObject':
            objectEnumeration.push({
                objectName: objectName,
                properties: { ... },
                selector: { ... }
            });
            break;
    };

    return objectEnumeration;
}
```

##properties
The properties in `enumerateObjectInstances` will reflect the properties you defined in your capabilities. See example at bottom of page. 

##selector
The selector in `enumerateObjectInstances` determines where each object will be bound in the dataView. There are four distinct options. 

####static 
This object will be bound to metadata `dataviews[index].metadata.objects`
```typescript
selector: null 
```
####columns 
This object will be bound to columns with the matching QueryName. 
```typescript
selector: {
    metadata: 'QueryName'
}
```
####scope identity 
This object will be bound to particular values of a column. For example, if I had a column 'Months' with 12 values ("jan", ..., "dec") I could loop over this column's DataViewScopeIdentity[] and set each identity as the selector.
```typescript
selector: {
    data: <DataViewScopeIdentity>identity
}
```
####selector 
This object will be bound to the element we have created a selectionID for. In this example, we will assume that we have created selectionIDs for some dataPoints, and we are looping through them.

```typescript
for (let dataPoint in dataPoints) {
    ...
    selector: dataPoint.selectionID.getSelector()
}
```

##Example:
In this example, we show what one objectEnumeration would look like for a customColor object with one property 'fill'. We want this object bound statically to `dataViews[index].metadata.objects`
```typescript
objectEnumeration.push({
    objectName: "customColor",
    displayName: "Custom Color",
    properties: {
        fill: {
            solid: {
                color: dataPoint.color
            }
        }
    },
    selector: null
});
```
