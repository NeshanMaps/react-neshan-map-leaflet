# ⚛️ React component for 🍃 Neshan Leaflet map.

## Getting started

In the simple case you just need to add `options` prop to `NeshanMap` component.


```javascript
import React from 'react';
import NeshanMap from 'react-neshan-map-leaflet'

function SimpleMap() {
  return (
    <NeshanMap
      options={{
        key: 'YOUR_API_KEY',
        center: [35.699739, 51.338097],
        zoom: 13
      }}
    />
  );
}

export default SimpleMap;

```

## Installation

npm:
```
npm install react-neshan-map-leaflet
```

## Features

### Neshan Maps API Loads on Demand

There is no need to place a `<script src=` tag at top of page. The Neshan Maps API loads upon the first usage of the `NeshanMap` component.

### Use Laflet Maps API 

You can access to Leaflet Maps `L` , `map`  objects by using `onInit`.

```javascript
...
<NeshanMap
  options={{
    key: 'YOUR_API_KEY',
    maptype: 'dreamy',
    poi: true,
    traffic: false,
    center: [35.699739, 51.338097],
    zoom: 13
  }}

  onInit={(L, myMap) => {
    let marker = L.marker([35.699739, 51.338097])
      .addTo(myMap)
      .bindPopup('I am a popup.');

    myMap.on('click', function (e) {
      marker.setLatLng(e.latlng)
    });

    L.circle([35.699739, 51.348097], {
      color: 'red',
      fillColor: '#f03',
      fillOpacity: 0.5,
      radius: 500
    }).addTo(myMap);
  }}
/>

```

[Example here](https://github.com/AliSeyfollahi/react-neshan-map-leaflet/blob/master/src/index.js#L8)

