#Using Capabilities

Capabilities are used to provide information to the host about your visual. All properties on the Capabilities model are ```optional```

Your visual's capabilities are loaded from

```json
{
    "dataRoles": [ ... ],
    "dataViewMappings": [ ... ],
    "objects":  { ... },
    "supportsHighlight": true|false,
    "sorting": { ... }
}

```


##Define the data fields your visual expects - `dataRoles`

To define fields that can be bound to data we use `dataRoles` which takes an array of `DataViewRole` objects which defines all of the properties needed.

###Properties

* **name** - the internal name of this data field (must be unique)
* **kind** - the kind of field:
    * 0 `Grouping` - Discrete values used for grouping of measure fields
    * 1 `Measure` - Numeric data values 
    * 2 `GroupingOrMeasure` - Can be used as either a grouping or measure
* **displayName** - the name displayed to the user in the properties pane
* **description** - a short description of the field (optional)

###Example

```json
"dataRoles": [
    {
        "displayName": "My Category Data",
        "name": "myCategory",
        "kind": 0
    },
    {
        "displayName": "My Measure Data",
        "name": "myMeasure",
        "kind": 1
    }
]
```

The above data roles would create the following fields

![](../images/DataRoleDisplay.png)


##Define how you want the data mapped - `dataViewMappings`

A DataViewMapping describes how the data roles relate to each other and allows you to specify conditional requirements for the them.

Most visuals provide a single mapping, but you can provide multiple dataViewMappings. Each valid mapping will produce a DataView. 

```json
"dataViewMappings": [
    {
        "conditions": [ ... ],
        "categorical": { ... },
        "table": { ... },
        "single": { ... },
        "matrix": { ... }
    }
]
```

[Learn more about DataViewMappings](DataViewMappings.md)


##Define property pane options - `objects`

Objects describe customizable properties associated with the visual.
Each object can have multiple properties and each property has a type associated with it.
Types refer to what the property will be. See below for more information about types.

```json
"objects": {
    "myCustomObject": {
        "displayName": "My Object Name",
        "properties": { ... }
    }
}
```

[Learn more about objects](Objects.md)

##Handle partial highlighting - `supportsHighlight`

By default this value is set to false which means your "Values" will be automatically filtered when something on the page is selected which will in turn update your visual to display just the selected value. If you want display the full data, but just highlight the selected items you need to set `supportsHighlight` to true in your capabilities.json.

[Learn more about highlighting](Highlighting.md)
