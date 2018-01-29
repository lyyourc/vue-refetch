# vue-refetch

Deal with `pending`, `error`, and `fullfill` local state for vue component when fetch data.

## Install

```bash
npm i -S vue-refetch
```

## Usage

The template,

```html
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
```

And the scripts,

```js
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
```
