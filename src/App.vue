<template>
  <div id="app">
    <div>
      <button @click="tabTheme">{{theme}}</button>
    </div>
    <HelloWorld msg="Welcome to Your Vue.js App" />
  </div>
</template>

<script>
import HelloWorld from './components/HelloWorld.vue'

export default {
  name: 'App',
  data () {
    return {
      theme: 'dark'
    }
  },
  components: {
    HelloWorld
  },
  methods: {
    tabTheme () {
      this.theme = this.theme === 'dark' ? 'light' : 'dark'
      window.document.documentElement.setAttribute("data-theme", this.theme)
    }
  },
  mounted () {
    window.document.documentElement.setAttribute("data-theme", this.theme)
  }
}
</script>

<style lang="scss">
#app {
  @include background_color();
  @include font_color();
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
}
</style>
