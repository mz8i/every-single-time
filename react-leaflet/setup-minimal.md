# Checklist for basic react-leaflet map

Technologies assumed:
- CRA
- React-Leaflet (verified on `3.2.0`)
- Leaflet (verified on `1.7.1`)


## Packages

Required for both JS and TS:
`react-leaflet leaflet`

Required additionally for TS:
`@types/react-leaflet @types/leaflet`

React-Leaflet typings won't work without Leaflet typings, e.g. you'll get an error about `TileLayer` having no `attribution` prop etc.

## Components
`App.(j|t)sx`:
```
import React from 'react';

import { MapContainer, TileLayer } from 'react-leaflet';

import 'leaflet/dist/leaflet.css'; // REQUIRED: Leaflet CSS
import './App.css';

export function App() {

    // REQUIRED: center prop on MapContainer
    // REQUIRED: zoom prop on MapContainer
    return (
      <div className="App">
        <MapContainer
          center={[51.505, -0.09]}
          zoom={13}
        >
          <TileLayer
            attribution='&copy; <a href="http://osm.org/copyright">OpenStreetMap</a> contributors'
            url="https://{s}.tile.openstreetmap.org/{z}/{x}/{y}.png"
          />
        </MapContainer>
      </div>
    );
}
```

## CSS

Add to `App.css` to maximise map to full page:
```
.leaflet-container {
  height: 100vh;
  width: 100%;
}
```
