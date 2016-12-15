# How to Submit a visual to Power BI Visual Gallery? 
## Submission and Publication  
After you have created and tested your custom visual, you may submit your visual [here](https://app.powerbi.com/visuals/info#submit). Below are the acceptance criteria and submission workflow which the custom visual team will follow in order to get your visual published in the Power BI visuals gallery.  

You can use [package validator tool](https://powerbi-validator-v-glpol.herokuapp.com) (TODO: fix to production link) for an artifact review of the your package.

### Visual Acceptance Criteria   
- Submission contains images:  
 - Screenshot for the visual details window - must be 410px (height) by 424px (width) (acceptable formats: png, jpg/jpeg or svg)  
 - Thumbnail for the gallery main page – must be 176px (height) by 220px (width) (acceptable formats: png, jpg/jpeg or svg)  
 - Icon (inside the pbiviz package) – must be 20px by 20px (acceptable formats: png, jpg/jpeg or svg)  
 - Images are in good quality 
- Privacy statement URL .  
- Legal (License) Terms URL. If not provided – confirm with the submitter that we will use our standard legal terms. We should send them a link to these standard legal terms.   
- Package contains all meta-data.  
 - Name    
 - Tooltip text (display name)    
 - Version    
 - Description    
 - Publisher Name    
 - Contact Email    
 - Support URL      
- Submission contains a sample pbix file with examples of the visual features.  
- JavaScript code review.    
 - The input data is validated before rendering.   
 - Visual doesn’t contain code that does unexpected network calls.     
 - Visual doesn’t contain code that does Power BI API calls.    
 - Visual doesn’t contain code that changes parent DOM elements.    
 - Visual doesn't contain obfuscated code.   
 - There are no timed jobs that can continue after the destroy method of the visual is called.
- CSS code review
 - Visual doesn’t contain code that rewrites global powerbi rules 
 - Visual doesn’t contain code that does suspicious rewrites of html tags rules 
 - Visual doesn’t contain only classes or IDs as left selector part (does not have tag as left part)
- All links to supporting documentation are active and valid.  
- See [Minimum requirements for implementing a new visual](https://github.com/Microsoft/PowerBI-visuals-core/wiki/Minimum-requirements-for-implementing-a-new-visual).
- All test cases (see [Test cases](./SubmissionTesting.md)) are passed.
- All items the [Common problems of custom visuals](./SubmissionCommonProblems.md) are addressed.

## Submission Flow  
1. Author submits a visual package and content.  
2. The Microsoft custom visual team reviews the visual and contents and provides a written report to the author identifying blocking and non-blocking issues.  
3. Author corrects any issues and re-submits the visual package.  
4. Once all blocking issues have been resolved, author provides a sample report, blog post and video highlighting the features and functions of the visual.  
5. Microsoft publishes the visual to the Power BI visual gallery.  
 
### Submission Tracking  
The custom visual team will stay in contact with you, via email, on the status of your visual submission. The team will provide you with feedback on the visual, blocking issues which will prevent the visual from being published, requests for any missing content, notification when your visual is ready to publish, and when the visual publication is complete.  

You could always check current status of your submission with [this service](https://powerbi-validator-v-glpol.herokuapp.com) (TODO: fix to production link). 
 
## Support for custom visuals  
Microsoft’s goal for the Power BI gallery is to provide high-quality visuals to enhance the use of Power BI for a rich user reporting experience. From time to time, we are notified that a visual in the gallery is not working properly or at all.  
Microsoft reserves the right to make emergency fixes to visuals from the community to ensure a positive user experience. If we make an emergency fix to a visual you have published, we will provide you with all coding changes so that they may be included in your next version release.  
 
 
