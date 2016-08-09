#DataViewMappings

A DataViewMapping describes how the data roles relate to each other and allows you to specify conditional requirements for the them.
There is a section for each of the `dataViews`.

Each valid mapping will produce a DataView, but currently we only support performing one query per visual so in most situations you will only get one DataView. However, you can provide multiple data mappings with different conditions which allow

```json
"dataViewMappings":[
    {
        "conditions": [ ... ],
        "categorical": { ... },
        "single": { ... },
        "table": { ... },
        "matrix": { ... }
    }
]
```

##Conditions

Describes conditions for a particular data mapping. You can provide multiple sets of conditions and if the data matches one of the described sets of conditions the visual will accept the data as valid.

Currently, for each field you can specify a min and max value. This represents the number of fields that can be bound to that data role. Note: if a data role is omitted in the condition, it can have any number of fields.

**Example 1**

By default, you can drag multiple fields into each data role. In this example we limit category to 1 data field and measure to 2 data fields.

```json
"conditions": [
    { "category": { "max": 1 }, "y": { "max": 2 } },
]
```

**Example 2**

In this example, one of two conditions are required. Either exactly 1 category data field and exactly 2 measures, or exactly 2 categories and exactly one measure.

```json
"conditions": [
    { "category": { "min": 1, "max": 1 }, "measure": { "min": 2, "max": 2 } },
    { "category": { "min": 2, "max": 2 }, "measure": { "min": 1, "max": 1 } }
]
```

##Single Data Mapping

Single data mapping is the simplest form of data mapping. It accepts a single measure field and gives you the total. If the field is numeric it will give you the sum. Otherwise it will give you a count of unique values.

To use single data mapping you simply define the name of the data role you want to map. This will only work with a single measure field. If a second field is assigned no data view will be generated so it is also good practice to include a condition that limits the data to a single field.

Note: This data mapping cannot be used in conjunction with any other data mapping. It is meant to reduce data into a single numeric value.

**Example**

```json
"dataViewMappings": {
    "conditions": [
        { "Y": { "max": 1 } }
    ],
    "single": {
        "role": "Y"
    }
}  
```

The resulting data view will still contain the other types (table, categorical, etc), but each mapping will only contain the single value. Best practice is to just access the value inside of single.

![](../images/DataViewMappingResultSingle.png)

##Categorical Data Mapping

Categorical data mapping is used to get one or two independent grouping of data.

**Example 1**
Here is the definition from our previous example on DataRoles..
```json
"dataRole":[
    {
        "displayName": "Category",
        "name": "category",
        "kind": 0
    },
    {
        "displayName": "Y Axis",
        "name": "measure",
        "kind": 1
    }
]
```
Now for the mapping:
```json
"dataViewMappings": {
    "categorical": {
        "categories": {
            "for": { "in": "category" }
        },
        "values": {
            "select": [
                { "bind": { "to": "measure" } }
            ]
        }
    }
}
```
This is a very simple example, in plain english it reads "Map my 'category' DataRole so that for every field I drag into 'category', its data is mapped to categorical.categories. Also map my 'measure' DataRole to categorical.values."

* **for...in** - For all the items in this data role, include them in the data query.
* **bind...to** - Produces the same result as for...in, but expects that the DataRole will have a condition restricting it to a single field.

**Example2**

In this example, we will use the first two DataRoles from the previous example, additionally defining "grouping" and "measure2".
```json
"dataRole":[
    {
        "displayName": "Category",
        "name": "category",
        "kind": 0
    },
    {
        "displayName": "Y Axis",
        "name": "measure",
        "kind": 1
    },
    {
        "displayName": "Grouping with",
        "name": "grouping",
        "kind": 0
    },
    {
        "displayName": "X Axis",
        "name": "measure2",
        "kind": 1
    }
]
```
Now for the mapping: 
```json
"dataViewMappings":{
    "categorical": {
        "categories": {
            "for": { "in": "category" }
        },
        "values": {
            "group": {
                "by": "grouping",
                "select":[
                    { "bind": { "to": "measure" } },
                    { "bind": { "to": "measure2" } }
                ]
            }
        }
    }
}
```
Here the difference is in how we are mapping categorical.values. We are saying "Map my 'measure' and 'measure2' DataRoles to be grouped by the DataRole 'grouping'." 

**Example3**
```json
Here are the dataRoles.
"dataRoles": [
    {
        "displayName": "Categories",
        "name": "category",
        "kind": 0
    },
    {
        "displayName": "Measures",
        "name": "measure",
        "kind": 1
    },
    {
        "displayName": "Series",
        "name": "series",
        "kind": 0
    }
]
```

Here are the dataViewMappings.
```json
"dataViewMappings": [
    {
        "categorical": {
            "categories": {
                "for": {
                    "in": "category"
                }
            },
            "values": {
                "group": {
                    "by": "series",
                    "select": [{
                            "for": {
                                "in": "measure"
                            }
                        }
                    ]
                }
            }
        }
    }
]
```

The categorical dataview could be visualized like this.
![](images/CategoricalData.png)

PowerBI will produce you this as the categorical dataview. This is the set of categories.
![](images/CategoricalDataView.png)

Each category maps to a set of values as well. Each of these values is grouped by series, which is years.
For example, Canada sales in 2013 is null, Canada sales in 2014 is 50.  
![](images/CategoricalValuesDataView.png)


##Table Data Mapping
The table data view is a simple data mapping. Essentially, it is a list of data points, where numeric data points could be aggregated.

**Example1**

With the given capabilities:

```json
"dataRoles": [
    {
        "displayName": "Values",
        "name": "values",
        "kind": 2
    }
]
```

```json
"dataViewMappings": [
    {
        "table": {
            "rows": {
                "for": {
                    "in": "values"
                }
            }
        }
    }
]
```

The table dataview could be visualized like this.  
![](images/TableData.png)

PowerBI will produce you this as the table dataview. Do not assume there is an ordering.  
![](images/TableDataView.png)

The data can be aggregated by selecting the desired field and clicking sum.  
![](images/DataAggregation.png)
