<template>
  <div>
    <div>{{ markdown }}</div>
    <div v-html="markdownToHtml"></div>
  </div>
</template>

<script>
import { marked } from 'marked'

export default {
  name: 'App',
  data() {
    return {
      markdown: '# Hello World'
    }
  },
  computed: {
    markdownToHtml() {
      return marked(this.markdown)
    },
  },
};
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
