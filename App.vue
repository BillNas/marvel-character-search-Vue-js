<template>
  <div id="app">
    <Search v-on:requestSearch="characterSearch"></Search>
    <Character v-bind:character=character></Character>
  </div>
</template>

<script>

import Search from './components/Search.vue'
import Character from './components/Character.vue'
import axios from 'axios'
export default {
  name: 'app',
  components:{
    Search , 
    Character,
    },
  data(){
    return{
          character : [],
     }
  },
  methods:{
    characterSearch(query){
      this.character = [];
     axios.get('https://gateway.marvel.com/v1/public/characters?name=' + query + '&limit=100&ts=1&limit=100&apikey=a08d9cbf68d4fffffdf7e1bfa5f0736f&hash=3223d61fc1a0a773a9674d1c715e0687')
  .then((res) =>{ 
    this.character=res.data.data.results[0];
    this.comics= res.data.data.results[0].comics.items
  })

    }
    },
  }

</script>

<style>
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  background:black;
  color:black;

}
</style>