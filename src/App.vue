<template>
  <!--<img alt="Vue logo" src="./assets/logo.png">-->
  <!--<HelloWorld msg="Welcome to Your Vue.js App"/>-->
  <!--<test/>-->
  <h1>{{ title }}</h1>
  <Modal header="Sign up for the Giveaway!" text="Grab your ninja swag for half price!"/>
</template>

<script>
//import HelloWorld from './components/HelloWorld.vue'
//import test from './components/test.vue'
//import test2 from './components/test2.vue'
import Modal from './components/Modal.vue'


export default {
  name: 'App',
  components: {
    Modal
  },
  data() {
    return {
      title: 'My First Vue App :)'
    }
  }
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
