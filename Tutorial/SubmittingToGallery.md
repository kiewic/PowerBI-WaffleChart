# How to submit a custom visual to the Power BI visuals gallery?

## Submission and publication

Once you've created and tested your custom visual, you can [submit it to the visuals gallery](https://app.powerbi.com/visuals/info#submit).

Below are the acceptance criteria and submission workflow which the custom visuals team will follow in order to get your visual published into the Power BI visuals gallery.

### Visual acceptance criteria

- Submission contains a valid and public link to GitHub repo with sources of your visual and sample data in it.
- Submission contains good quality images:
 - Screenshot for the visual details window - must be 424px (width) by 410px (height) (acceptable formats: png, jpg/jpeg or svg).
 - Thumbnail for the gallery main page – must be 220px (width) by 176px (height) (acceptable formats: png, jpg/jpeg or svg).
 - Icon (inside the pbiviz package) – must be 20px by 20px (acceptable formats: png, jpg/jpeg or svg).
- Privacy statement URL.  
- Legal (License) Terms URL. If not provided – we will use our [standard legal terms](https://powerbi.microsoft.com/en-us/visuals-gallery-terms/).   
- Package contains all meta-data:
 - Visual Name, as it will appear in the gallery and the visualization pane once user imports it into the report
 - Tooltip text (display name)
 - Version
 - Description, for the visual details page in the gallery
 - Publisher Name
 - Contact Email
 - Support URL, where users will go to get support for the visuals
 - GitHub repository URL
- Submission contains a sample report pbix file with examples of the visual features
- JavaScript code review:
 - The input data is validated before rendering
 - Visual doesn’t contain code that does unexpected network calls
 - Visual doesn’t contain code that does Power BI API calls
 - Visual doesn’t contain code that changes parent DOM elements
 - Visual doesn't contain obfuscated code
 - There are no timed jobs that can continue after the destroy method of the visual is called
- CSS code review:
 - Visual doesn’t contain code that rewrites global powerbi rules
 - Visual doesn’t contain code that does suspicious rewrites of html tags rules
 - Visual contains only classes or IDs as left selector part (does not have tag as left part)
- All links to supporting documentation are active and valid
- Review [Minimum requirements for implementing a new visual](https://github.com/Microsoft/PowerBI-visuals-core/wiki/Minimum-requirements-for-implementing-a-new-visual)
- All test cases (see [Test cases](./SubmissionTesting.md)) are passed
- All items from [Common problems of custom visuals](./SubmissionCommonProblems.md) are addressed

## Submission flow

1. Author submits a visual package and content.
2. The Microsoft custom visuals team reviews the visual and contents and provides a written report to the author identifying blocking and non-blocking issues.
3. Author corrects any issues and re-submits the visual package.
4. Once all blocking issues have been resolved, author provides a sample report, blog post and video highlighting the features and functions of the visual.
5. Microsoft publishes the visual to the Power BI visual gallery.

***NOTE:** once published to the gallery, the custom visual goes through deployment rings to ensure the quality of the visual by exposing it to a limited set of users that gradually goes wider as the visuals goes through the different rings. It will take about 3 weeks for the custom visual to appear in the public gallery, if there was no breaking change detected in any of the deployment rings.*

### Submission tracking

The custom visuals team will contact you for the status of your visual submission. The team will provide you with feedback on the visual, blocking issues which will prevent the visual from being published, requests for any missing content, notification when your visual is ready to publish, and when the visual publication is complete.

## Support for custom visuals

Microsoft’s goal for the Power BI visuals gallery is to have high-quality visuals to provide a rich user reporting experience. From time to time, we are notified that a visual in the gallery is not working properly or at all.
Microsoft reserves the right to fix visuals from the community to ensure a good user experience. If we make such fix to a visual you have published, we will provide you with all coding changes so that they may be included in your next version release.
