<template>
  <div id="app">
   <Autocomplete :items="customers"/>
  </div>
</template>

<script>
import customers from './assets/customers';
import Autocomplete from './components/Autocomplete.vue'

export default {
  name: 'App',
  components: {Autocomplete},

 mounted(){
   this.customers = customers;
   console.log(this.customers)
 },

data(){
  return{
    customers:[]
  }
}

}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;

}
</style>
