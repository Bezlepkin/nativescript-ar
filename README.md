NativeScript Augmented Reality
==============================

> Work in progress. Implementation-details may change, and this README for sure will 😄

> You'll need to install Xcode 9 to run AR on iOS.

> Android support will be added, but there's currently hardly anyone on the planet with an Android device capable of running AR anyway.

## Usage with Angular

- Browse to the module where you want to show off some AR goodness and add:

```typescript
import { registerElement } from "nativescript-angular/element-registry";
registerElement("AR", () => require("nativescript-ar").AR);
```

- Open a view that's in the same module (or you've added it to the global app module) and add:

```html
<GridLayout rows="auto, *" class="page">
    <Label row="0" text="Scan a surface, then tap it like crazy!" class="p-20" horizontalAlignment="center"></Label>
    <AR row="1">
        <!-- you can add layouts here if you like to overlay the AR view -->
    </AR>
</GridLayout>
```

- Open its component and add:

```typescript
// import
import { AR } from "nativescript-ar";

  constructor() {
    // if this is false on a modern iOS 11 device, rebuild in Xcode
    console.log("AR supported? " + AR.isSupported());
  }
```