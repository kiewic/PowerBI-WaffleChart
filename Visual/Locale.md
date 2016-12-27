#Getting Locale in Custom Visuals 

Visuals can now know PowerBI's locale, so they can display localized information.
(read more about [Supported languages and countries/regions for Power BI](https://powerbi.microsoft.com/en-us/documentation/powerbi-supported-languages/))

For example, getting locale in the sample BarChart.

![Sample BarChart with Locale](../images/LocaleInSampleBarChart.png)

Each of these bar charts was created under different locale (English, Basque and Hindi), and it is displayed in the tooltip.

##Getting the 'locale'

The 'locale' is passed as a string during the initialization of the visual. If a locale is changed in PowerBI the visual will be generated again with the new locale.
You can find the full sample code at [SampleBarChart with Locale - UPDATE LINK!!!](https://github.com/Microsoft/PowerBI-visuals-sampleBarChart/commit/981b021612d7b333adffe9f723ab27783c76fb14)

The BarChart contructor now has a `locale` member which is instantiated in the constructor with the host `locale` instance.

```typescript
        private locale: string;

        this.locale = options.host.locale;
```

### Supported Locales
            ar-SA: العربية (Arabic)
            bg-BG: български (Bulgarian)
            ca-ES: català (Catalan)
            cs-CZ: čeština (Czech)
            da-DK: dansk (Danish)
            de-DE: Deutsche (German)
            el-GR: ελληνικά (Greek)
            en-US: English (English)
            es-ES: español service (Spanish)
            et-EE: eesti (Estonian)
            eU-ES: Euskal (Basque)
            fi-FI: suomi (Finnish)
            fr-FR: français (French)
            gl-ES: galego (Galician)
            he-IL: עברית (Hebrew)
            hi-IN: हिन्दी (Hindi)
            hr-HR: hrvatski (Croatian)
            hu-HU: magyar (Hungarian)
            id-ID: Bahasa Indonesia (Indonesian)
            it-IT: italiano (Italian)
            ja-JP: 日本の (Japanese)
            kk-KZ: Қазақ (Kazakh)
            ko-KR: 한국의 (Korean)
            it-LT: Lietuvos (Lithuanian)
            lv-LV: Latvijas (Latvian)
            ms-MY: Bahasa Melayu (Malay)
            nb-NO: norsk (Norwegian)
            nl-NL: Nederlands (Dutch)
            pl-PL: polski (Polish)
            pt-BR: português (Portuguese)
            pt-PT: português (Portuguese)
            ro-RO: românesc (Romanian)
            ru-RU: русский (Russian)
            sk-SK: slovenský (Slovak)
            sl-SI: slovenski (Slovenian)
            sr-Cyrl-RS: српски (Serbian)
            sr-Latn-RS: srpski (Serbian)
            sv-SE: svenska (Swedish)
            th-TH: ไทย (Thai)
            tr-TR: Türk (Turkish)
            uk-UA: український (Ukrainian)
            vi-VN: tiếng Việt (Vietnamese)
            zh-CN: 中国 (Chinese-Simplified)
            zh-TW: 中國 (Chinese-Tranditional)
        
        