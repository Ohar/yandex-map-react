# yandex-map-react

## Quick start

```js
import React from 'react';
import ReactDOM from 'react-dom';
import { Map, Marker, MarkerLayout } from 'yandex-map-react';

export default function ContactMap (props) {
    render () {
        return (
            <Map onAPIAvailable={function () { console.log('API loaded'); }} center={[55.754734, 37.583314]} zoom={10}>
                <Marker lat={this.props.lat} lon={this.props.lon} />
            </Map>
        );
    }
}
```

## Installation

`yandex-map-react` requires React >= 0.14

### npm

```
npm install --save yandex-map-react
```

## Parameters

| Parameter | Default value | Type | Decription |
|---------|-----------------------|---------|----------|
| `width` | 600 | Number | container width |
| `height` | 600 | Number | container height |
| `style` | {} | Object | styles that will be applied to container element |
| `loadOptions` | {lang: 'ru_RU', coordorder: 'latlong', load: 'package.full', mode: 'release'} | Object | API loading [params](https://tech.yandex.ru/maps/doc/jsapi/2.1/dg/concepts/load-docpage/). Enabled params: `lang`, `apikey`, `coordorder`, `load`, `mode` |
| [Supported YandexMap API params](https://tech.yandex.com/maps/doc/jsapi/2.1/ref/reference/Map-docpage/) |
| `center` | [55, 45] | Array[Number] | coordinates of map center |
| `zoom` | 10 | Number | zoom level |
| `state` | {controls: []} | Object | describe map state (ex. [controls](https://tech.yandex.com/maps/doc/jsapi/2.1/ref/reference/Map-docpage/#param-state.controls)) |
| Callbacks |
| `onAPIAvailable` | - | Function | callback will be invoked as soon as YandexMAP API available |

## Events

Components support API events, to handle convert first letter of event name to uppercase and add `on` to begin. Example: `mousemove` -> `onMousemove` ([description](https://tech.yandex.com/maps/doc/jsapi/2.1/ref/reference/IDomEventEmitter-docpage/#event-mousemove)).

## Features

Custom Geoobject marker [layout](https://tech.yandex.com/maps/doc/jsapi/2.1/ref/reference/GeoObject-docpage/#param-options.iconLayout). Custom balloon layout - soon.

```js
<Marker lat={55.783379} lon={37.775575}>
    <MarkerLayout>
        <div style={{borderRadius: '50%', overflow: 'hidden'}}>
            <img src="http://loremflickr.com/80/80"/>
        </div>
    </MarkerLayout>
</Marker>
```

## Examples

https://github.com/effrenus/yandex-map-react-examples/

## License

MIT (http://www.opensource.org/licenses/mit-license.php)
