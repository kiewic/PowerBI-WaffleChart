# Enabling and Disabling Interactivity in Custom Visuals 

Visuals can query the value of the 'allowInteractions' flag, that indicate whether the visual should allow visual interactions.
For example, visuals should be interactive during report viewing or editing, but not interactive when viewed in a dashboard.
These interactions are click, pan, zoom, selection, etc.
Note, that tooltips are expected be enabled in all scenarios, regardless of this flag.

## Getting the 'allowInteractions' value

The 'allowInteractions' flag is passed as a boolean during the initialization of the visual, as a member of the [IVisualHost interface](IVisualHost.md).

In any Power BI scenario that requires the visuals not to be interactive (e.g. Dashboard tiles) - 'allowInteractions' flag will be set to false.
Otherwise (e.g. Report), 'allowInteractions' will be set to true.
You can find the full sample code at [SampleBarChart with allowInteractions](https://github.com/Microsoft/PowerBI-visuals-sampleBarChart/commit/???)

```typescript
   ...
   let allowInteractions = options.host.allowInteractions;
   bars.on('click', function(d) {
       if (allowInteractions) {
           selectionManager.select(d.selectionId); 
           ...
       }
   });
```