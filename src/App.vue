<template>
  <div id="app">
    <h1>dynamic components demonstration</h1>
    <component v-bind:is="cmp"></component>
    <button v-on:click="updatecmp('signin')"> Sign in </button>
    <button v-on:click="updatecmp('signup')"> Sign up </button>  
  </div>
</template>

<script>
import signIn from './components/signIn.vue'
import signUp from './components/signUp.vue'
export default {
  name: 'App',
  components: {
    'signin':signIn,
    'signup':signUp
  },
  data(){
    return {cmp:'signin'}
  },
  methods:{
    updatecmp(item){
      this.cmp=item
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
