# Developer guide to building a professional custom visual for Power BI

## General  words about requirements of good-looking visual.

## Validation of the dataset (expect any type of data here) and supporting big datasets. Links to examples of proper validation.

## Supporting wide variety of formatting options. Less hardcoded settings/more options for user to specify.

## Supporting cross-filtering when available. Links to new API documentation.

## Tips and tricks

Check [Common problems of custom visuals](./SubmissionCommonProblems.md)


## Versioning.

Current versioning has the following format: **xx.xx.xx**. The first number is major version, second is minor, third is patch/hotfix.

**MAJOR.MINOR.PATCH**

**MAJOR** version is incremented when you make incompatible API changes.

1. changes that are done after incompatible changes in infrastructure code or

2. changes that require user to update his report that contains this visual - because visual does not support previous version of settings.

**MINOR** version is changed when you add functionality/feature in a backwards-compatible manner.

**PATCH** (or HOTFIX) version is changed when you make backwards-compatible bug fixes. 

Every package submission needs to have different version.


## Unit tests and manual tests.

To provide high-quality visuals to the Power BI community, it is important to fully test your visual before submission to the gallery. Upon receipt of your visual submission, the Power BI custom visual team will use these test cases and acceptance criteria to validate your submission.

You can use package [validator tool](https://powerbi-validator-v-glpol.herokuapp.com/) (TODO: fix to production link) for an artifact review of the your package.

### Best Practices

1. The behavior of your visual should be the same in mobile, web and desktop versions of Power BI application. And mobile-friendly at the same time in terms of touch support and tooltip appearance, 

2. Use a different type of data and datasets. Do not rely only on your sample dataset that was used for development of the custom visual.

3. Test critical situations – multiple instances on the same page or the same report, big datasets, different types of data, user input and formatting settings, etc.

4. Ensure that elements of your visual will not overlap each other on different sizes of your visual, different type of datasets and different formatting settings.

5. Set min/max fields of your data roles to limit the number of fields that can be dropped into the specific field bucket.

6. Add unit tests that will validate your visual ensuring that new changes do not break your visual.

Also check our [test cases and acceptable web browsers](./SubmissionTesting.md).
