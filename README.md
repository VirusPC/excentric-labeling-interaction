# Excentric Labeling

[![](https://img.shields.io/npm/l/excentric-labeling?registry_uri=https%3A%2F%2Fregistry.npmjs.com)](https://github.com/VirusPC/excentric-labeling/blob/master/LICENSE)

## Introduction


Excentric labeling interaction is based on the [excentric labeling layout algrithm](https://github.com/VirusPC/excentric-labeling). It allows you to augment your scatter plot, bar chart, tree map or any other visualizatoins with labeling technique in a few lines of code!

## Live Demo
- [live demo](https://excentric-labeling-react.vercel.app/)
- [source code](https://github.com/VirusPC/excentric-labeling-react) 

## Usage

[see here](https://github.com/VirusPC/excentric-labeling-react/blob/0c60a3b068ad04ba49f77d52be8c2731d7c610da/src/components/render-using-d3.js#L46)

```ts
import excentricLabeling from "excent";
import eli from "excentric-labeling-interaction";

const {addExcentricLabelingInteraction, computeSizeOfLabels} = eli;

// 1. rendering
const {mainLayer, coordinatesWithInfo} = renderScatterPlot(g, width, height, data, fieldX, fieldY, fieldColor, interactionParams, setStateFuncs);

// 2. interaction
// 2.1 precompute lable size of each point
/** @type {{x: number, y: number, color: string, label: string,labelWidth: number, labelHeight: number}} */
const rawInfos = computeLabelSizeEachPoint(coordinatesWithInfo, svg, interactionParams.fontSize);
// 2.2 add interaction
addExcentricLabelingInteraction(mainLayer, width, height, rawInfos, interactionParams);

function computeLabelSizeEachPoint(points, root, fontSize) {
  const rawInfos = points.map((point) => {
    return {
      x: point.x,
      y: point.x,
      color: point.color,
      label: point.label,
      labelWidth: 0,
      labelHeight: 0,
    };
  });
  computeSizeOfLabels(rawInfos, root, fontSize);
  return rawInfos;
}
```

