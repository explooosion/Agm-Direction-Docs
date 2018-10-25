# Marker

<hr>

### Usage

Useful features.

### Example

##### ⭐️ Custom Icons

![Image](https://i.imgur.com/FaLnz7A.png)

```html
<agm-direction ... 
    [renderOptions]="renderOptions" 
    [markerOptions]="markerOptions"
>
</agm-direction>
```

```typescript
public renderOptions = {
    suppressMarkers: true,
}

public markerOptions = {
    origin: {
        icon: 'https://www.shareicon.net/data/32x32/2016/04/28/756617_face_512x512.png',
        draggable: true,
    },
    destination: {
        icon: 'https://www.shareicon.net/data/32x32/2016/04/28/756626_face_512x512.png',
        label: 'MARKER LABEL',
        opacity: 0.8,
    },
}
```

##### ⭐️ Custom infoWindow

You need to create custom marker to use infoWindow.

- infoWindow: string | (default: *addr* )

![Image](https://i.imgur.com/FLCk1Ix.png)

```html
<agm-direction ... 
    [renderOptions]="renderOptions" 
    [markerOptions]="markerOptions"
>
</agm-direction>
```

```typescript
public renderOptions = {
    suppressMarkers: true,
}

public markerOptions = {
    origin: {
        icon: 'https://i.imgur.com/7teZKif.png',
    },
    destination: {
        icon: 'https://i.imgur.com/7teZKif.png',
        infoWindow: `
        <h4>Hello<h4>
        <a href='http://www-e.ntust.edu.tw/home.php' target='_blank'>Taiwan Tech</a>
        `
    },
}
```

##### ⭐️ Multiple directions one infoWindow
 
When click marker, other infoWindow will be closed.

![img](https://user-images.githubusercontent.com/13682994/41510320-f14a259e-7294-11e8-925c-719f1a88d2a8.gif)

```html
<agm-direction 
    [origin]="origin1" 
    [destination]="destination1" 
    [waypoints]="waypoints" 
    [renderOptions]="renderOptions" 
    [markerOptions]="markerOptions" 
    [infowindow]="infoWindow" 
    (sendInfowindow)="obtainInfowindow($event)"
>
</agm-direction>
<agm-direction 
    [origin]="origin2" 
    [destination]="destination2" 
    [waypoints]="waypoints" 
    [renderOptions]="renderOptions" 
    [markerOptions]="markerOptions" 
    [infowindow]="infoWindow" 
    (sendInfowindow)="obtainInfowindow($event)"
>
</agm-direction>
```

```typescript
import { InfoWindow } from '@agm/core/services/google-maps-types' // option
```

```typescript
public origin1: Object = { lat: 24.799448, lng: 120.979021 };
public destination1: Object = { lat: 24.799524, lng: 120.975017 };

public origin2: Object = { lat: 24.798448, lng: 120.972021 };
public destination2: Object = { lat: 24.789524, lng: 120.972017 };

public renderOptions = {
    suppressMarkers: true,
}

public markerOptions = {
    origin: {
        icon: 'https://i.imgur.com/7teZKif.png',
    },
    destination: {
        icon: 'https://i.imgur.com/7teZKif.png',
        infoWindow: `
        <h4>Hello<h4>
        <a href='http://www-e.ntust.edu.tw/home.php' target='_blank'>Taiwan Tech</a>
        `
    },
};

public infoWindow: InfoWindow = undefined;

public obtainInfowindow(window: InfoWindow) {
    this.infoWindow = window
}
```