# Input

<hr>

### Usage

The `DirectionsRequest` object literal contains the following fields:

👉 [DirectionsRequest](https://developers.google.com/maps/documentation/javascript/directions?hl=en#DirectionsRequests)

```typescript
origin: { lat: Number, lng: Number }
destination: { lat: Number, lng: Number }
travelMode: string = 'DRIVING'
transitOptions: any = undefined
drivingOptions: any = undefined
waypoints: object = []
optimizeWaypoints: boolean = true
provideRouteAlternatives: boolean = false
avoidHighways: boolean = false
avoidTolls: boolean = false
renderOptions: any
visible: boolean = true
panel: object | undefined
markerOptions: { origin: any, destination: any }
```