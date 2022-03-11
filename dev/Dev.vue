<template>
  <div id="app">
    <v-select
      @option:cleared="clearedOption"
      v-model="selected"
      v-bind="config"
      label="name"
      @option:selected="selectedOption"
    >
      <template #clear-button></template
    ></v-select>
    {{ selected }}
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
        {
          name: 'Brother',
          id: '46604eb3d8e10106739d5162ab1b5caf',
        },
        {
          name: 'Canon',
          id: '56528d326f0339102056231ca03eb2aa',
        },
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
    selectedOption(value) {
      selected = value
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
