# Direction

<hr>

### Usage

Useful features.

### Example

##### Remove Direction

![img](https://camo.githubusercontent.com/773ab0686eb4b3ec0acef716eb58985727bd4c34/68747470733a2f2f692e696d6775722e636f6d2f686c39395956582e676966)

```html
<agm-direction [visible]="show"></agm-direction>
<button type="button" (click)="removeDirection()">Remove</button>
<button type="button" (click)="showDirection()">Show</button>
```

```typescript
public show: boolean = true
public removeDirection(){
    this.show = false
}
public showDirection(){
    this.show = true
}
```

##### Update Panel With New Query

![Image](https://camo.githubusercontent.com/80f24aa149b5f06f28bf5f85d739b2e559510928/68747470733a2f2f692e696d6775722e636f6d2f6932484a4c46422e676966)

```html
<agm-direction *ngIf="dir" 
    [origin]="dir.origin" [destination]="dir.destination"
    [panel]="#myPanel">
</agm-direction>
<div #myPanel></div>
<button type="button" (click)="getDirection_A()">Direction_A</button>
<button type="button" (click)="getDirection_B()">Direction_A</button>
```

```typescript
public dir = undefined
public getDirection_A() {
    this.dir = {
        origin: { lat: 24.799448, lng: 120.979021 },
        destination: { lat: 24.799524, lng: 120.975017 }
    }
}
public getDirection_B() {
    this.dir = {
        origin: { lat: 24.799748, lng: 120.974021 },
        destination: { lat: 24.792524, lng: 120.975517 }
    }
}
```