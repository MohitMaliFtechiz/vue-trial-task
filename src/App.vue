<template>
  <div id="app">    
    <TextElement textelement="Hi" v-bind:items="items"/>
  </div>
</template>

<script>
import TextElement from './components/TextElement.vue'

export default {
  name: 'App',
  components: {
    TextElement
  },
  props:{
    'text': String
  },
  data() {
    return {
      textelement: '',
      list: ['Hi','My Lovely','little', 'Ponny'] ,
      items: [
        {isHidden: false , text: 'hi' , changeTextColor: false , fontSize: 10},
        {isHidden: false , text: 'My Lovely' , changeTextColor: false , fontSize: 10},
        {isHidden: false , text: 'little' , changeTextColor: false , fontSize: 10},
        {isHidden: false , text: 'Ponny' , changeTextColor: false , fontSize: 10}
      ]
    }
  },
 methods: {
   createElement() {      
      this.textelement = this.text;    
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
