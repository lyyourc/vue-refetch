# vue-refetch

Fetch data for Vue component

## Install

```bash
npm i -S vue-refetch
```

## Usage

The template,

```html
<template>
<div>
  <vue-refetch :src="{ userFetch }">
    <div slot-scope="{ userFetch }">
      {{ userFetch.name }}
    </div>

    <div slot="pending">
      loading...
    </div>

    <div slot="error">
      error
    </div>
  </vue-refetch>
</div>
</template>
```

And the scripts,

```js
<scripts>
import vueRefetch from 'vue-refetch'

export default {
  components: { vueRefetch },
  methods: {
    userFetch() {
      return new Promise(resolve => {
        setTimeout(() => resolve({ name: 'foo' }))
      })
    }
  }
}
</scripts>
```
