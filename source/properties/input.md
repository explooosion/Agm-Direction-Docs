# Input

<hr>

### Usage

The `DirectionsRequest` object literal contains the following fields:

👉 [DirectionsRequest](https://developers.google.com/maps/documentation/javascript/directions?hl=en#DirectionsRequests)

```typescript
public origin: LatLng | string | google.maps.Place
public destination: LatLng | string | google.maps.Place
public travelMode: string = 'DRIVING'
public transitOptions: any = undefined
public drivingOptions: any = undefined
public waypoints: object = []
public optimizeWaypoints: boolean = true
public provideRouteAlternatives: boolean = false
public avoidHighways: boolean = false
public avoidTolls: boolean = false
public renderOptions: any
public visible: boolean = true
public panel: object | undefined
public markerOptions: { 
    origin: { 
        infoWindow: string,
        ...
    }, 
    destination: { 
        infoWindow: string,
        ... 
    } 
}
```

### Example

##### ⭐️ origin

```html
<agm-direction ... [origin]="origin"></agm-direction>
```

```typescript
public origin: any = { lat: 24.799448, lng: 120.979021 }

// or

public origin: string = 'Taipei Main Station'
```

##### ⭐️ destination

```html
<agm-direction ... [destination]="destination"></agm-direction>
```

```typescript
public destination: any = { lat: 24.799524, lng: 120.975017 }

// or

public destination: string = 'Taiwan Presidential Office'
```

##### ⭐️ [travelMode](https://developers.google.com/maps/documentation/javascript/reference#TravelMode)

```html
<agm-direction ... [travelMode]="travelMode"></agm-direction>
```

```typescript
public transitOptions: string = 'TRANSIT' // default: 'DRIVING'
```

##### ⭐️ [transitOptions](https://developers.google.com/maps/documentation/javascript/reference#TransitOptions)

```html
<agm-direction ... [travelMode]="travelMode" [transitOptions]="transitOptions"></agm-direction>
```

```typescript
public transitOptions: string = 'TRANSIT'
public transitOptions: any = {
    departureTime: new Date('2018/05/20 13:14'),
    arrivalTime: new Date('2018/05/20 13:30'),
    modes: ['BUS'],
}
```

##### ⭐️ [drivingOptions](https://developers.google.com/maps/documentation/javascript/reference#DrivingOptions)

```html
<agm-direction ... [drivingOptions]="drivingOptions"></agm-direction>
```

```typescript
public drivingOptions: any = {
    departureTime: new Date('2018/05/20 13:14'),
    arrivalTime: new Date('2018/05/20 13:30'),
    modes: ['BUS'],
}
```

##### ⭐️ [waypoints](https://developers.google.com/maps/documentation/javascript/reference#DirectionsWaypoint)

```html
<agm-direction ... [waypoints]="waypoints"></agm-direction>
```

```typescript
public waypoints: object = [
    {
        location: { lat: myLat, lng: myLng },
        stopover: true,
    },
    {
        location: 'Joplin, MO',
        stopover: false,
    },{
        location: 'Oklahoma City, OK',
        stopover: true,
    }]
```

##### ⭐️ [optimizeWaypoints](https://developers.google.com/maps/documentation/javascript/reference#DirectionsRequest)

```html
<agm-direction ... [waypoints]="waypoints" [optimizeWaypoints]="optimizeWaypoints"></agm-direction>
```

```typescript
public waypoints: object = [...]
public optimizeWaypoints: boolean = false // default: true
```

##### ⭐️ [provideRouteAlternatives](https://developers.google.com/maps/documentation/javascript/reference#DirectionsRequest)

```html
<agm-direction ... [waypoints]="waypoints" [provideRouteAlternatives]="provideRouteAlternatives"></agm-direction>
```

```typescript
public waypoints: object = [...]
public provideRouteAlternatives: boolean = true // default: false
```

##### ⭐️ [avoidHighways](https://developers.google.com/maps/documentation/javascript/reference#DirectionsRequest)

```html
<agm-direction ... [avoidHighways]="avoidHighways"></agm-direction>
```

```typescript
public avoidHighways: boolean = true // default: false
```

##### ⭐️ [avoidTolls](https://developers.google.com/maps/documentation/javascript/reference#DirectionsRequest)

```html
<agm-direction ... [avoidTolls]="avoidTolls"></agm-direction>
```

```typescript
public avoidTolls: boolean = true // default: false
```

##### ⭐️ [renderOptions](https://developers.google.com/maps/documentation/javascript/reference#DirectionsRendererOptions)

```html
<agm-direction ... [renderOptions]="renderOptions"></agm-direction>
```

```typescript
public renderOptions: any = {
    draggable: true,
    suppressMarkers: true,
    suppressInfoWindows: false,
    markerOptions: { // effect all markers
        icon: 'your-icon-url',
    },
}
```

##### ⭐️ visible

```html
<agm-direction ... [visible]="visible"></agm-direction>
```

```typescript
public visible: boolean = false // default: true
```

##### ⭐️ [panel](https://developers.google.com/maps/documentation/javascript/examples/directions-panel?hl=en)

```html
<agm-direction ... [panel]="myPanel"></agm-direction>
<div #myPanel></div
```

or

```html
<agm-direction ... [panel]="setPanel()"></agm-direction>
<div id="myPanel"></div>
```

```typescript
public setPanel() {
    return document.querySelector('#myPanel');
}
```

##### ⭐️ [markerOptions](https://developers.google.com/maps/documentation/javascript/reference?hl=zh-tw#MarkerOptions)

```html
<agm-direction ... [renderOptions]="renderOptions" [markerOptions]="markerOptions"></agm-direction>
```

```typescript
public renderOptions = {
    suppressMarkers: true,
}

public markerOptions = {
    origin: {
        infoWindow: 'This is origin.'
        icon: 'your-icon-url',
        draggable: true,
    },
    destination: {
        icon: 'your-icon-url',
        label: 'marker label',
        opacity: 0.8,
    },
}
```

##### ⭐️ infoWindow

```html
<agm-direction ... [infoWindow]="infoWindow"></agm-direction>
```

```typescript
import { InfoWindow } from '@agm/core/services/google-maps-types' // option
```

```typescript
public infoWindow: InfoWindow = undefined
```