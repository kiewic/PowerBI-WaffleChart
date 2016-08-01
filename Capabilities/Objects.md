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