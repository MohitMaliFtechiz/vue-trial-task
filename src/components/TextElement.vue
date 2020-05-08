<template>
  <!-- <div class="hello">
    <h1>{{ msg }}</h1>
    
  </div> -->
  <div class="relative-position cursor_normal none_outline"
     style="color: rgb(255, 255, 255); opacity: 1; border-radius: 6px; transform: rotate(0deg); border: 0px solid rgb(70, 144, 247); padding: 10px; text-align: center; letter-spacing: 0px; font-size: 32px; font-family: Aleo; font-weight: 300; text-decoration: none; box-shadow: rgb(0, 0, 0) 0px 0px 0px 0px; text-transform: initial; font-style: normal; z-index: 2002; text-shadow: rgba(0, 0, 0, 0.2) 2px 2px 0px; line-height: 1.5em;"
     spellcheck="false">

  <!-- <span style="background-color: rgb(248, 187, 208); padding-left:3px; padding-right: 3px; border-radius: 4px;margin-right: 5px;" v-for="(item, index) in list" v-bind:key="index" v-on:click="showButtons($event)">{{ item }}  <br>  
  </span> -->
  
  <span :style="item.changeTextColor ? { 'color': 'red' } : null" class="text" v-for="(item, index) in items" v-bind:key="index" v-on:click="showButtons(item)">{{ item.text }} <br>
  <div v-if="item.isHidden">
    <button class="button-green" v-on:click="changeColor(item)">Change Color</button>
    <button class="button-blue">Enlarge Text</button>
    <button class="button-orange"> Change Background Color </button>
  </div>  
  </span>

</div>
</template>

<script>
export default {
  name: 'TextElement', 
  props: {
    textelement: String,
    items: Array
  },
  methods: {
    showButtons(item){
      for(var i=0;i<this.items.length;i++){
        if(this.items[i].text == item.text){
            this.items[i].isHidden = true;
        }
      }      
    },
    changeColor(item){
      for(var i=0;i<this.items.length;i++){
        if(this.items[i].text == item.text){
            this.items[i].changeTextColor = true;
        }
      }   
     
    }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
h3 {
  margin: 40px 0 0;
}
ul {
  list-style-type: none;
  padding: 0;
}
li {
  display: inline-block;
  margin: 0 10px;
}
a {
  color: #42b983;
}
.button-green {
  background-color: #4CAF50; /* Green */
  border: none;
  color: white;
  padding: 12px 15px;
  text-align: center;
  text-decoration: none;
  display: inline-block;
  font-size: 12px;
  box-shadow: 0 8px 16px 0 rgba(0,0,0,0.2), 0 6px 20px 0 rgba(0,0,0,0.19);
  margin-right: 10px;
}
.button-blue {
  background-color: #008CBA; /* Blue */
  border: none;
  color: white;
  padding: 12px 14px;
  text-align: center;
  text-decoration: none;
  display: inline-block;
  font-size: 12px;
  box-shadow: 0 8px 16px 0 rgba(0,0,0,0.2), 0 6px 20px 0 rgba(0,0,0,0.19);
  margin-right: 10px;
}
.button-orange {
  background-color: #f4511e; /* orange */
  border: none;
  color: white;
  padding: 12px 7px;
  text-align: center;
  text-decoration: none;
  display: inline-block;
  font-size: 12px;
  box-shadow: 0 8px 16px 0 rgba(0,0,0,0.2), 0 6px 20px 0 rgba(0,0,0,0.19);
  margin-right: 10px;
}
.text{
  background-color: rgb(248, 187, 208); padding-left:3px; padding-right: 3px; border-radius: 4px;margin-right: 5px;
}
</style>
