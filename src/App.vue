<template>
  <div class="container">
    <div class="wrapper-one">
      <textarea v-model="markdown"></textarea>
    </div>
    <div class="wrapper-two">
      <div v-html="markdownToHtml"></div>
    </div>
  </div>
</template>

<script>

export default {
  name: 'App',
  data() {
    return {
      markdown: 
      `**Isto é um** editor de markdown.  
      **A edição ocorre em** _tempo real_
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
}

body {
  margin: 0;
  padding: 0;
  font-family: sans-serif;
  background: #f5f5f5;
}

.container {
  display: flex;
  flex-direction: row;
  justify-content: space-between;
}

.wrapper-one {
  width: 50%;
  height: 100vh;
  /* background-color: red; */
  border-right: #2c3e50 solid 1px;
}

.wrapper-two {
  padding-top: 60px;
  width: 50%;
  height: 100vh;
  /* background-color: blue; */
  font-size: 20px;
}

textarea {
  width: 80%;
  height: 90vh;
  border: none;
  background-color: transparent;
  font-size: 20px;
  padding: 60px;
}
</style>