<template>
  <div>
    <div>{{ markdown }}</div>
    <textarea v-model="markdown"></textarea>
    <div v-html="markdownToHtml"></div>
  </div>
</template>

<script>

export default {
  name: 'App',
  data() {
    return {
      markdown: 
      `**Hello World:** Teste  
      **Continua aqui:** Teste 2  
      Fin
      `
    }
  },
  computed: {
    markdownToHtml() {
      return this.marked(this.markdown)
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
