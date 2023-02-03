<template>
  <ChatView />
</template>

<script>
import ChatView from './components/ChatView.vue'

export default {
  name: 'App',
  components: {
    ChatView
  }
}
</script>

<style>
* {
  margin: 0;
}

#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  height: 100vh;
}
</style>
