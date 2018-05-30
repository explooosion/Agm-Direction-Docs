# Output

<hr>

### Usage

The `DirectionsResult` object will emit when sending a directions request.

👉 [DirectionsResult](https://developers.google.com/maps/documentation/javascript/directions?hl=en#DirectionsResults)

```typescript
public onChange: EventEmitter<any> = new EventEmitter<any>()
```

### Example

##### onChange

```html
<agm-direction (onChange)="changeHandler($event)"></agm-direction>
```

```typescript
public changeHandler(event: any){
  console.log(event);
  // You can do anything.
}
```

