#Enabling and Disabling Interactivity in Custom Visuals 

Visuals can query the value of the 'allowInteractions' hint, suggesting whether to allow interactions within the visual.
For example, visuals should not be interactive when rendered as a tile in a dashboard.
In this case - the 'allowInteractions' flag will be set to false, allowing the visual to block interactions and render in a "View only" mode.

##Getting the 'allowInteractions' value

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