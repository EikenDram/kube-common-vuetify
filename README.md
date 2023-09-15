# kube-common-vuetify

Base vuetify components

## Installing as git submodule in vuetify project

```sh
git submodule add https://github.com/EikenDram/kube-common-vuetify src/common
```

## Adding components as vue plugin

`plugins/kube-common-vuetify.ts`
```ts
import type { App } from "vue";
import * as common from "../common";

export default {
  install: (app: App) => {
    Object.entries(common).forEach(([key, value]) => {
      app.component(key, value);
    });
  },
};
```

`plugins/index.ts`
```ts
import common from './kube-common-vuetify'

  app
    .use(common)
```