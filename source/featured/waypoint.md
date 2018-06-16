# Waypoint

<hr>

### Usage

Useful features.

### Example

##### ⭐️ Saving Draggable Directions's Waypoint

```html
<agm-direction ...
    [waypoints]="waypoints" [renderOptions]="renderOptions" 
    (onChange)="change($event)">
</agm-direction>
```

```typescript
public waypoints: any = []
public renderOptions = {
    draggable: true,
}
public change(event: any) {
    this.waypoints = event.request.waypoints;
}
```