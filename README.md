# react-xml-viewer
Simple and configurable React component to prettify XMLs, now supporting React 18.

This is a fork of https://github.com/alissonmbr/react-xml-viewer and the only adjustment done so far was bumping up the peer dependency version for React.

[![NPM](https://img.shields.io/npm/v/react-xml-viewer.svg)](https://www.npmjs.com/package/react-xml-viewer) [![JavaScript Style Guide](https://img.shields.io/badge/code_style-standard-brightgreen.svg)](https://standardjs.com)

<img src="https://raw.githubusercontent.com/alissonmbr/react-xml-viewer/master/example/example-ss.png" width="300"/>

## Install

```bash
npm install --save react-xml-viewer-2
```

## Usage

```jsx
import React, { Component } from 'react'
import XMLViewer from 'react-xml-viewer-2'

const xml = '<hello>World</hello>'

export default class App extends Component {
  render () {
    return (
      <div>
        <XMLViewer xml={xml} />
      </div>
    )
  }
}
```

## Props
### xml (string)
A xml string to prettify.
**Default**: undefined
**Example**: `<hello>World</hello>`

### indentSize (number)
The size of the indentation.
**Default**: 2

### invalidXml (node)
When the xml is invalid, invalidXml will be returned.
**Default**: <div>Invalid XML!</div>

### collapsible (bool)
Allow collapse/expand tags by click on them
When tag is collapsed its content and attributes are hidden. Only <tag></tag> is shown
**Default**: false
### theme (object)

| Key | Type | Default | Description |
| --- | ---- | ------- | ----------- |
| attributeKeyColor | color | #2a7ab0 | set the attribute key color (`<tag attribute-key="hello" />`) |
| attributeValueColor | color | #008000 | set the attribute value color (` <tag attr="Attribute value">`) |
| cdataColor | color | #1D781D | set the cdata element color (`<![CDATA[some stuff]]>`) |
| commentColor | color | #aaa | set the comment color (`<!-- this is a comment -->`)
| separatorColor | color | #333 | set the separators colors (`<, >, </, />, =, <?, ?>`)
| tagColor | color | #d43900 | set the tag name color (`<tag-name />`) |
| textColor | color | #333 | set the text color (`<tag>Text</tag>`)|
| overflowBreak | bool | false | adjust the xml to fit in the parent width without overflowing|

**Example**:
Changing attribute key and value color
``` jsx
import React, { Component } from 'react'
import XMLViewer from 'react-xml-viewer'

const xml = '<hello attr="World" />'
const customTheme = {
  "attributeKeyColor": "#FF0000",
  "attributeValueColor": "#000FF"
}

export default class App extends Component {
  render () {
    return (
      <div>
        <XMLViewer xml={xml} theme={customTheme} />
      </div>
    )
  }
}
```

## Run with typescript
If you have difficulties to run with typescript declare module 'react-xml-viewer-2' to react-app-env.d.ts


## License

MIT © [alissonmbr](https://github.com/alissonmbr)
