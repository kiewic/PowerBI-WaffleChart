# Common problems of custom visuals 
The custom visuals team has written and reviewed many custom visuals. Some of the common issues found with custom visuals are: 

1. Input dataView is not validated when it is converted to internal data model.  
Do not expect that dataView will always have required properties and arrays are filled in. You should clear your visual’s content if you don’t have enough information provided to display it – for example when a mandatory field bucket is not filled in. Also, do not assume that type of data from the dataset will be only the one you expected.  
This problem causes errors to be thrown from the update method of the visual and unexpected behavior when the visual is updated. 
2. Labels and elements of the visual are overlapped.  
Use a different type of datasets to fully test your visual with various sets of elements of your visual. Resize your visual to check how elements of the visual are responding to that. Increase/decrease text sizes if property pane provides those settings. 
This problem causes overlapping of elements of the visual. Such issues are critical when you cannot interact with an element that is overlapped. 
3. Numeric settings of the property pane are not validated in the code of the visual. 
Test values provided by the property pane. This problem causes performance issues, console errors, or even crashing of the visual. 
4. The visual throws errors in the console of the browser. 
Any issue of the visual causing such errors should be fixed. 
5. Data labels are not formatted. 
Use different types of data to check if the data labels are formatted well. 
6. Duplicated icon image definitions in CSS file are caused by the current version of Dev Tools. 
7. Version of the visual is not increased after update. 
8. The GUID of the visual is changed even if the visual is already published.  
The GUID of the visual can be found in package.json, css and js files of the package
