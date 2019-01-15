# snabbel

snabbel is library that provides some components and functions to use [snabbdom](https://github.com/snabbdom/snabbdom) in [objectel](https://github.com/ENvironmentSet/objectel) well.

## API

### VDOM({ [modules], [container], [children] })

| Arguments | Description |
|-----------|-------------|
| modules | modules for `snabbdom.init`, check [snabbdom's document](https://github.com/snabbdom/snabbdom#modules-documentation) about this. default value is empty array. |
| container | Root of Virtual dom. default value is DOM Fragment. |
| children | elements which will be applied vdom's event stream. |

* returns an element

Examples

Simple Counter

```jsx harmony
import { VDOM } from 'snabbel';
import * as Ol from 'objectel';

import Counter from './Counter';
import IncreaseButton from './IncreaseButton';

const app = document.getElementById('app');
const globalEventBus = Ol.createEventBus();
const vdom = (
  <VDOM container={app}>
    <Counter />
    <IncreaseButton amount={100} />
  </VDOM>
);

globalEventBus.Emit$(vdom(globalEventBus.Listen$));

```