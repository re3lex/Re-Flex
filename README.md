![re-flex](./resources/img/re-flex-banner.png)

# About Re-F|ex

Re-F|ex is a React flex-based layout component library which I created because none of the components I found out there could satisfy my requirements.

It intends to address in a simple way the needs of advanced React Web applications that require resizable layouts.

Here is a basic demo:

```js
import ReactDOM from 'react-dom'
import React from 'react'

import {
  ReflexContainer,
  ReflexSplitter,
  ReflexElement
} from 'react-reflex'

import 'react-reflex/styles.css'

/////////////////////////////////////////////////////////
// Basic vertical re-flex layout with splitter
// Adding a splitter between two ReflexElements
// will allow the user to resize them
//
/////////////////////////////////////////////////////////
class ReflexDemo extends React.Component {

  render () {

    return (
      <ReflexContainer orientation="vertical">

        <ReflexElement className="left-pane">
          <div className="pane-content">
            Left Pane (resizeable)
          </div>
        </ReflexElement>

        <ReflexSplitter/>

        <ReflexElement className="right-pane">
          <div className="pane-content">
            Right Pane (resizeable)
          </div>
        </ReflexElement>

      </ReflexContainer>
    )
  }
}

ReactDOM.render(
  <ReflexDemo/>,
  document.getElementById('reflex-demo'))
```

## Installation

```sh
npm install react-reflex
```

ES6, CommonJS, and UMD builds are available with each distribution.

```js
// You will need to import the styles separately
// You probably want to do this just once during the bootstrapping phase of your application.
import 'react-reflex/styles.css'

// then you can import the components
import {
  ReflexContainer,
  ReflexSplitter,
  ReflexElement
} from 'react-reflex'
```

You can also use the UMD build
```html
<link rel="stylesheet" href="path-to-react-reflex/styles.css">
<script src="path-to-react-reflex/dist/umd/react-reflex.min.js"></script>
```

## React Support

React >= 0.13.x

## Browser Support

Re-F|ex is responsive, mobile friendly and has been tested on the following browsers:

  * Chrome
  * Firefox
  * Safari
  * Opera
  * Edge
  * IE11

## Documentation & Samples

Re-F|ex is the most powerful resizeable React layout component out there ... Don't just trust me, try it!

[Click here for code samples and live demos ...](https://leefsmp.github.io/Re-Flex/index.html)

![re-flex-demo](https://cdn.rawgit.com/leefsmp/data/f3ec837d/Re-Flex/demo.gif)

* Supported properties on `ReflexContainer`:

  * `orientation`: Orientation of the layout container. Default value: `horizontal`. Type: `oneOf(['horizontal', 'vertical'])`.
  
  * `maxRecDepth`: Maximun recursion depth to solve initial flex of layout elements based on user provided values. This prevents infinite recursion in case the constraints solver cannot find suitable dimensions on the elements to satisfy initial inputs. Default value: `100`. Type: `number`.
  
  * `className`: Space separated classnames to apply custom styles on the component. Default value: `empty string ''`. Type: `string`.
  
  * `style`: allows passing inline style to the container. Default value: `{}`. Type: `object`.

* Supported properties on `ReflexElement`:

  * `propagateDimensions`: Setting this to `true` will propagate a dimensions `{height, width}` property to the children. See [Size-aware element demo](https://leefsmp.github.io/Re-Flex/index.html#demo7) for more details. Default value: `false`. Type: `bool`.

  * `propagateDimensionsRate`: When resizing with `propagateDimensions={true}`, defines the rate at which the dimensions will be updated on the child elements (in times per second). This can help improving performances when using this approach on heavy components by skipping some rerender steps during resizing. Default value: `100`. Type: `number`.
  
  * `resizeHeight`: Allows to control if `height` will be propagated when `propagateDimensions={true}`. Default value: `true`. Type: `bool`.
  
  * `resizeWidth`: Allows to control if `width` will be propagated when `propagateDimensions={true}`. Default value: `true`. Type: `bool`.

  * `size`: Allows to control the size in pixel of an element. The main use-case is to allow to perform animations programmatically on an element (shrinking/expanding). See [Controlled elements demo](https://leefsmp.github.io/Re-Flex/index.html#demo6) for more details. Default value: `true`. Type: `number`.

  * `direction`: Allows to control in which direction(s) the element will shrink/expand when its `size` property is modified. See [Controlled elements demo](https://leefsmp.github.io/Re-Flex/index.html#demo6) for more details. Default value: `1`. Type: `-1, 1 or [-1, 1]`.

  * `onStartResize`: Event fired when user initiates layout resizing. Default value: `undefined`. Type: `function({domElement, component})`.

  * `onStopResize`: Event fired when user finishes layout resizing. Default value: `undefined`. Type: `function({domElement, component})`.
  
  * `onResize`: Event fired at each resize step when user resizes layout. Default value: `undefined`. Type: `function({domElement, component})`.

  * `className`: Space separated classnames to apply custom styles on the component. Default value: `empty string ''`. Type: `string`.

  * `style`: allows passing inline style to the container. Default value: `{}`. Type: `object`.

* Supported properties on `ReflexSplitter`:

  * `propagate`: Propagate the drag when reszing a layout across multiple splitters. Layou must have at least 3 elements with therefore 2 splitters for this properties to be relevant. Default value: `false`.Type: `bool`.

  * `onStartResize`: Event fired when user initiates layout resizing. Default value: `undefined`. Type: `function({domElement, component})`.

  * `onStopResize`: Event fired when user finishes layout resizing. Default value: `undefined`. Type: `function({domElement, component})`.
  
  * `onResize`: Event fired at each resize step when user resizes layout. Default value: `undefined`. Type: `function({domElement, component})`.

  * `className`: Space separated classnames to apply custom styles on the component. Default value: `empty string ''`. Type: `string`.

  * `style`: allows passing inline style to the container. Default value: `{}`. Type: `object`.



## Development

* Build the lib: `npm run build` | `npm run build-dev` (dev mode non-minified with source-map)
* Build the demo: `npm run build-demo` | `npm run build-demo-dev` (dev mode non-minified with source-map + webpack watch)

## Web Applications using Re-F|ex

  [See here...](./webapps-using-reflex.md)
  
  (Feel free to add your own by submitting a pull request...)

## About the Author

[https://twitter.com/F3lipek](https://twitter.com/F3lipek)
