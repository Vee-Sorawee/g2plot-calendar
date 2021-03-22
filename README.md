# G2Plot-Calendar

> G2Plot-Calendar: plugin based on G2Plot v2. [CodeSandbox](https://codesandbox.io/s/g2plot-calendar-p6418).

[![npm Version](https://img.shields.io/npm/v/g2plot-calendar.svg)](https://www.npmjs.com/package/g2plot-calendar)
[![npm License](https://img.shields.io/npm/l/g2plot-calendar.svg)](https://www.npmjs.com/package/g2plot-calendar)


![image](https://user-images.githubusercontent.com/7856674/103057591-e0b3d100-45da-11eb-8806-9c654bb84615.png)


## Install

```bash
$ npm i --save g2plot-calendar
```


## Usage

 - render

```ts
import { P } from '@antv/g2plot';
import * as G2PlotCalendar from 'g2plot-calendar';

let plot;

fetch('https://gw.alipayobjects.com/os/antfincdn/nvYn7dOQB9/result.json')
  .then((data) => data.json())
  .then((data) => {
    // 第一次默认渲染
    plot = new P('container', {}, G2PlotCalendar.adaptor, {
      ...G2PlotCalendar.defaultOptions,
      width: 240,
      height: 240,
      data,
    });

    plot.render();
  });
```

 - update

```ts
plot.update({
  data: [],
});
```

 - browser

```
<script src="https://unpkg.com/@antv/g2plot@2"></script>
<script src="https://unpkg.com/g2plot-calendar@1"></script>
<script>
  fetch('https://gw.alipayobjects.com/os/antfincdn/nvYn7dOQB9/result.json')
    .then((data) => data.json())
    .then((data) => {
      // 第一次默认渲染
      var calendarPlot = new G2Plot.P('calendar-result', {}, G2PlotCalendar.adaptor, {
        ...G2PlotCalendar.defaultOptions,
        width: 240,
        height: 240,
        data,
      });

      calendarPlot.render();
    });
</script>
```

## Configure

```ts
type Datum = {
  date: string;
  value: number | null;
};

export interface CalendarOptions {
  /** 数据 */
  readonly data: Datum[];
}
```

## License

MIT@[visiky](https://github.com/visiky).
