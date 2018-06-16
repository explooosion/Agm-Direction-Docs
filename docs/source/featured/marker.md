# Marker

<hr>

### Usage

Useful features.

### Example

##### ⭐️ Custom Icons

![Image](https://i.imgur.com/FaLnz7A.png)

```html
<agm-direction ... [renderOptions]="renderOptions" [markerOptions]="markerOptions"></agm-direction>
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

- infoWindow: string | (default: *addr* )

![Image](https://i.imgur.com/FLCk1Ix.png)

```html
<agm-direction ... [renderOptions]="renderOptions" [markerOptions]="markerOptions"></agm-direction>
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