# Getting the locale in Power BI for custom visuals 

Visuals can retrieve the PowerBI locale, in order to localize their content to the relevant language.
(read more about [Supported languages and countries/regions for Power BI](https://powerbi.microsoft.com/en-us/documentation/powerbi-supported-languages/))

For example, getting locale in the sample BarChart.

![Sample BarChart with Locale](../images/LocaleInSampleBarChart.png)

Each of these bar charts was created under a different locale (English, Basque and Hindi), and it is displayed in the tooltip.

## Getting the `locale`

The 'locale' is passed as a string during the initialization of the visual. If a locale is changed in PowerBI the visual will be generated again with the new locale.
You can find the full sample code at [SampleBarChart with Locale](https://github.com/Microsoft/PowerBI-visuals-sampleBarChart/commit/388670c71a873bf7412e771164ea3cbb8522a63e)

The BarChart contructor now has a `locale` member which is instantiated in the constructor with the host `locale` instance.

```typescript
    private locale: string;
    ...
    this.locale = options.host.locale;
```

### Supported Locales
Locale string | Language
--------------|----------------------
ar-SA | العربية (Arabic)
bg-BG | български (Bulgarian)
ca-ES | català (Catalan)
cs-CZ | čeština (Czech)
da-DK | dansk (Danish)
de-DE | Deutsche (German)
el-GR | ελληνικά (Greek)
en-US | English (English)
es-ES | español service (Spanish)
et-EE | eesti (Estonian)
eU-ES | Euskal (Basque)
fi-FI | suomi (Finnish)
fr-FR | français (French)
gl-ES | galego (Galician)
he-IL | עברית (Hebrew)
hi-IN | हिन्दी (Hindi)
hr-HR | hrvatski (Croatian)
hu-HU | magyar (Hungarian)
id-ID | Bahasa Indonesia (Indonesian)
it-IT | italiano (Italian)
ja-JP | 日本の (Japanese)
kk-KZ | Қазақ (Kazakh)
ko-KR | 한국의 (Korean)
lt-LT | Lietuvos (Lithuanian)
lv-LV | Latvijas (Latvian)
ms-MY | Bahasa Melayu (Malay)
nb-NO | norsk (Norwegian)
nl-NL | Nederlands (Dutch)
pl-PL | polski (Polish)
pt-BR | português (Portuguese)
pt-PT | português (Portuguese)
ro-RO | românesc (Romanian)
ru-RU | русский (Russian)
sk-SK | slovenský (Slovak)
sl-SI | slovenski (Slovenian)
sr-Cyrl-RS | српски (Serbian)
sr-Latn-RS | srpski (Serbian)
sv-SE | svenska (Swedish)
th-TH | ไทย (Thai)
tr-TR | Türk (Turkish)
uk-UA | український (Ukrainian)
vi-VN | tiếng Việt (Vietnamese)
zh-CN | 中国 (Chinese-Simplified)
zh-TW | 中國 (Chinese-Tranditional)

> **Note**: In the [PowerBI Desktop](https://www.microsoft.com/en-us/download/details.aspx?id=45331) the `locale` property will contain the language of the [PowerBI Desktop](https://www.microsoft.com/en-us/download/details.aspx?id=45331) installed.

# Localizing the property pane for custom visuals

The fields in the property pane (that are defined in the capabilities) can be localized to provide a more integrated and coherent experience, making your custom visual behave like any other PowerBI core visual.

For example, a non-localized custom visual created by using the 'pbiviz new' command,
will show the following fields in the property pane:

![non-Localized Property Pane](../images/propertyPane.png)

both the Category Data and the Measure Data are defined in the capabilities.json file as 'displayName'.

# How to localize capabilities

First add a display name key to every display name you want to localize in your capabilities.
In this example:

![Adding Display Name Keys](../images/displayNameKey.png)

Then add a directory called `stringResources`, this directory will contain all your different string resource files based on the locales you want your visual to support.
Under this directory you'll need to add a JSON file for every locale you want to support that contains the locale information and the localized strings values for every displayNameKey you want to replace.

In our example, lets say we want to support Arabic and Hebrew.
we will need to add two JSON files in the following way:

![Adding String Resources](../images/stringResourcesFiles.png)

Every JSON file defines a single locale (this has to be one of the locales from the supported list above),
with the string values for the desired display name keys.
In our example the Hebrew string resource file will look as follows:

![Hebrew String Resource](../images/hebrewStringResource.png)

After adding all the string resource files you'll need to add the path to your files in the pbiviz.json:

![Adding StringResources Paths](../images/stringResourcePath.png)

The resulting property pane will contain the displayName according to the string resource files you defined.
In our example, in case we change the language to Hebrew we will get the following property pane:

![Localized Property Pane](../images/localizedPropertyPane.png)
