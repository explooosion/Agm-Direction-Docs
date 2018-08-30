# [Agm-Direction-Docs](https://github.com/explooosion/Agm-Direction-Docs)

[![forthebadge](https://forthebadge.com/images/badges/for-sharks.svg)](https://forthebadge.com)
[![forthebadge](https://forthebadge.com/images/badges/built-with-love.svg)](https://github.com/GitbookIO/gitbook-cli)
[![forthebadge](https://forthebadge.com/images/badges/makes-people-smile.svg)](https://www.facebook.com/Remake.AON/)

[Agm-Direction](https://github.com/explooosion/Agm-Direction) is the directive for [@agm/core](https://github.com/SebastianM/angular-google-maps) (not official)

- Angular 2+
- Google Map API
- [Playground](https://stackblitz.com/edit/angular-lwchvs)  

### 👉 [Start Reading](http://robby570.tw/Agm-Direction-Docs)

![Agm-Direction](https://i.imgur.com/DCIoXqS.jpg)

## Installation

Installation is done using the
[`npm install` command](https://docs.npmjs.com/getting-started/installing-npm-packages-locally):

+ Install @agm/core
  ```bash
  npm install --save @agm/core
  ```

+ Install agm-direction
  ```bash
  npm install --save agm-direction
  ```

## Importing Modules

📦 [@agm/core](https://www.npmjs.com/package/@agm/core)  
📦 [agm-direction](https://www.npmjs.com/package/agm-direction)  

```typescript
import { BrowserModule } from '@angular/platform-browser';
import { NgModule } from '@angular/core';
import { AppComponent } from './app.component';

import { AgmCoreModule } from '@agm/core';            // @agm/core
import { AgmDirectionModule } from 'agm-direction';   // agm-direction

@NgModule({
  declarations: [
    AppComponent
  ],
  imports: [
    BrowserModule,
    AgmCoreModule.forRoot({ // @agm/core
      apiKey: 'your key',
    }),
    AgmDirectionModule      // agm-direction
  ],
  providers: [],
  bootstrap: [AppComponent]
})
export class AppModule { }
```

## Usage

HTML

```html
<button type="button" (click)="getDirection()">Get</button>

<agm-map [latitude]="lat" [longitude]="lng">
  <agm-direction [origin]="origin" [destination]="destination">
  </agm-direction>
</agm-map>
```

CSS

```css
agm-map {
    height: 400px;
}
```

TS

```typescript
public lat = 24.799448
public lng = 120.979021

public origin = { lat: 24.799448, lng: 120.979021 }
public origin = { lat: 24.799524, lng: 120.975017 }
```

## Boilerplate
Fork from [gitbook-boilerplate](https://github.com/explooosion/gitbook-boilerplate).


### Run local

```bash
git clone https://github.com/explooosion/Agm-Direction-Docs.git
```

```bash
npm install -g gitbook-cli
```

```bash
gitbook update
```

```bash
yarn dev
```

## License

[MIT](http://opensource.org/licenses/MIT)
