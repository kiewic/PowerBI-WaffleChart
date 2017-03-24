# Adding External Libraries
* [Including JavaScript files](#including-javascript-files)
* [Including CSS files](#including-css-files)

## Including JavaScript files
1. Install an external JavaScript library by using any package manager (npm, yarn, etc.)
2. Include a path of the library to the ```externalJS``` property of the ```pbiviz.json```

Please pay attention to [this](Typings.md) if you'd like to add typings for your JavaScript file to get intellisense and compile time safety on them.

### Example
* Installing [d3](https://www.npmjs.com/package/d3) by using [npm](https://www.npmjs.com/)

```bash
npm install d3@3.5.5 --save
```

* Including ```d3``` to the ```pbiviz.json```

```json
{
  "visual": {...},
  "apiVersion": ...,
  "author": {...},
  "assets": {...},
  "externalJS": [
    "node_modules/d3/d3.min.js"
  ],
  "style": ...,
  "capabilities": ...,
  "dependencies": ...
}
```

Please visit [this](https://github.com/Microsoft/powerbi-visuals-sankey/blob/c8200da56913cd8b253be949a35fad0f4472b6de/pbiviz.json#L22) page to find the real example.

## Including CSS files
1. Install an external CSS framework by using any package manager (npm, yarn, etc.)
2. Include the ```import``` statement to the ```.less``` file of the visual

### Example
* Installing [bootstrap](https://www.npmjs.com/package/bootstrap) by using [npm](https://www.npmjs.com/)

```bash
npm install bootstrap --save
```

* Include the ```import``` statement to the ```visual.less```

```less
@import (less) "node_modules/bootstrap/dist/css/bootstrap.css";
```

Please visit [this](https://github.com/Microsoft/powerbi-visuals-sankey/blob/c8200da56913cd8b253be949a35fad0f4472b6de/style/visual.less#L32) page to find the real example.
