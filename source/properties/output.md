# Output

<hr>

### Usage

The `DirectionsResult` object will emit when sending a directions request.

👉 [DirectionsResult](https://developers.google.com/maps/documentation/javascript/directions?hl=en#DirectionsResults)

```typescript
public onChange: EventEmitter<any> = new EventEmitter<any>()
```

### Example

##### ⭐️ onChange

```html
<agm-direction ... (onChange)="changeHandler($event)"></agm-direction>
```

```typescript
public changeHandler(event: any){
  console.log(event);
  // You can do anything.
}
```

##### ⭐️ sendInfoWindow

Only one infoWindow to be open at one time in multiple directions.

See [Multiple directions one infoWindow](http://robby570.tw/Agm-Direction-Docs/source/featured/marker.html)

```html
<agm-direction ... [infoWindow]="infoWindow" (sendInfoWindow)="obtainInfowindow($event)"></agm-direction>
```
```typescript
import { InfoWindow } from '@agm/core/services/google-maps-types' // option
```

```typescript
public infoWindow: InfoWindow = undefined

public obtainInfowindow(window: InfoWindow) {
  this.infoWindow = window
}
```