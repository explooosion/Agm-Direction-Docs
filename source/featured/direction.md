# Direction

<hr>

### Usage

Useful features.

### Example

##### ⭐️ Remove Direction

![img](https://camo.githubusercontent.com/773ab0686eb4b3ec0acef716eb58985727bd4c34/68747470733a2f2f692e696d6775722e636f6d2f686c39395956582e676966)

```html
<agm-direction ... [visible]="show"></agm-direction>
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

##### ⭐️ Update Panel With New Query

![Image](https://camo.githubusercontent.com/80f24aa149b5f06f28bf5f85d739b2e559510928/68747470733a2f2f692e696d6775722e636f6d2f6932484a4c46422e676966)

```html
<agm-direction 
    *ngIf="dir" 
    [origin]="dir.origin" 
    [destination]="dir.destination" 
    [panel]="#myPanel"
>
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

##### ⭐️ Load multiple directions [avoid query limit]

![Image](https://user-images.githubusercontent.com/13682994/64004882-c8948480-cb41-11e9-8a83-70d74e8ec849.png)

```html
<agm-map>
    <agm-direction
        *ngFor="let dir of directions"
        [visible]="done"
        [origin]="dir.origin"
        [destination]="dir.destination"
    >
    </agm-direction>
</agm-map>
<h1 style="text-align: center">Load: {{!done}}</h1>
```

```typescript

public directions: any = [];
public done = false;

ngOnInit() {
const dynamic = [{
    origin: { lat: Number(24.7992116), lng: Number(120.974784) },
    destination: { lat: Number(24.7994235), lng: Number(120.971342) },
},
{
    origin: { lat: Number(24.7984561), lng: Number(120.977411) },
    destination: { lat: Number(24.7989161), lng: Number(120.976215) },
},
{
    origin: { lat: Number(24.7963123), lng: Number(120.971211) },
    destination: { lat: Number(24.7969451), lng: Number(120.972611) },
},
{
    origin: { lat: Number(24.7944416), lng: Number(120.974444) },
    destination: { lat: Number(24.7945116), lng: Number(120.976612) },
},
{
    origin: { lat: Number(24.7942116), lng: Number(120.978184) },
    destination: { lat: Number(24.7947726), lng: Number(120.9789124) },
},
{
    origin: { lat: Number(24.7912135), lng: Number(120.971184) },
    destination: { lat: Number(24.7924125), lng: Number(120.969914) },
}];

this.directions = dynamic;
setTimeout(() => { this.done = true; }, 1500);
}
```

