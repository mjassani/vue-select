<template>
  <div id="app">
    <v-select
      @option:cleared="clearedOption"
      v-model="selected"
      v-bind="config"
      label="name"
    >
      <template #clear-button></template
    ></v-select>
  </div>
</template>

<script>
import vSelect from '../src/components/Select'
import countries from '../docs/.vuepress/data/manufacturers'
import books from '../docs/.vuepress/data/books'

export default {
  components: { vSelect },
  data: () => ({
    selected: null,
    config: {
      options: countries,
      topResults: [
        'Brother',
        'Canon',
        'DELL',
        'Epson',
        'HP',
        'Lexmark',
        'Samsung',
        'XEROX',
      ],
    },
  }),
  methods: {
    clearedOption() {
      alert('option cleared')
    },
  },
}
</script>

<style>
html,
body {
  margin: 0;
  height: 100%;
  font-family: -apple-system, sans-serif;
}

#app {
  height: 100%;
  max-width: 20rem;
  margin: 10rem auto 0;
}

hr {
  background: lightgray;
  border: none;
  height: 2px;
  margin-bottom: 32px;
  position: relative;
  top: 16px;
}

li.vs__dropdown-option:hover {
  background: var(--vs-dropdown-option--active-bg);
  color: var(--vs-dropdown-option--active-color);
}
</style>
