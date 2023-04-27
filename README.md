# Excentric Labeling

[![](https://img.shields.io/npm/l/excentric-labeling?registry_uri=https%3A%2F%2Fregistry.npmjs.com)](https://github.com/VirusPC/excentric-labeling/blob/master/LICENSE)

## Introduction


Excentric labeling interaction is based on the [excentric labeling layout algrithm](https://github.com/VirusPC/excentric-labeling). It allows you to augment your scatter plot, bar chart, tree map or any other visualizatoins with labeling technique in a few lines of code!

## Live Demo
- [live demo](https://excentric-labeling-react.vercel.app/)
- [source code](https://github.com/VirusPC/excentric-labeling-react) 

## Usage

```ts
import excentricLabeling from "excent";

import {addExcentricLabelingInteraction, computeSizeOfLabels}  from "excentric-labeling-interaction";

const {mainLayer, coordinatesWithInfo} = renderScatterPlot(g, width, height, data, fieldX, fieldY, fieldColor, interactionParams, setStateFuncs);

  // interaction
const rawInfos = getRawInfos(coordinatesWithInfo, svg, interactionParams.fontSize);
addExcentricLabelingInteraction(mainLayer, width, height, rawInfos, interactionParams, {
    onMove: (rawInfos, nearest) => {
        const rp = randomPoint(rawInfos);
        setStateFuncs.setCurLabel(nearest?.label || "");
        setStateFuncs.setRandomLabel(rp?.label || "");
    }
});
```

