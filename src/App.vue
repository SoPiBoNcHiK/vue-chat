<template>
  <div id="app">
    <Container :chatInfo="chatInfo"/>
  </div>
</template>

<script>
import Container from './components/Container.vue'


export default {
  name: 'App',
  components: {
    Container,
  },
  data() {
    return {
      chatInfo: {
        username : 'Ivan',
        datetime : '21.12.2019 23:20:0',
      },
    };
  },
}
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
