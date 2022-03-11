<template>
  <div id="app">
    <v-select
      @option:cleared="clearedOption"
      v-model="selected"
      v-bind="config"
    >
      <template #clear-button></template
    ></v-select>
  </div>
</template>

<script>
import vSelect from '../src/components/Select'
import countries from '../docs/.vuepress/data/countries'
import books from '../docs/.vuepress/data/books'

export default {
  components: { vSelect },
  data: () => ({
    selected: null,
    config: {
      options: countries,
      topResults: ['Afghanistan', 'Albania'],
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
  border: none;
  border-bottom: 1px solid #cacaca;
  margin-bottom: 1em;
  padding-top: 1em;
  width: 90%;
}
</style>
