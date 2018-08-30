# Output

<hr>

### Usage

The `DirectionsResult` object will emit when sending a directions request.

👉 [DirectionsResult](https://developers.google.com/maps/documentation/javascript/directions?hl=en#DirectionsResults)

```typescript
@Output() onChange: EventEmitter<any> = new EventEmitter<any>()

@Output() onResponse: EventEmitter<any> = new EventEmitter<any>()

@Output() sendInfoWindow: EventEmitter<InfoWindow> = new EventEmitter<InfoWindow>();
```

### Example

##### ⭐️ onChange

```html
<agm-direction ... (onChange)="onChange($event)"></agm-direction>
```

```typescript
public onChange(event: any){
  console.log(event);
  // You can do anything.
}
```

##### ⭐️ onResponse

```html
<agm-direction ... (onResponse)="onResponse($event)"></agm-direction>
```

```typescript
public onResponse(event: any){
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