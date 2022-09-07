<template>
  <div>
    <h1>{{name}}</h1>
    <h2 v-text="language"></h2>
    <h3 v-html="content"></h3>
    <h4>{{bindit}}</h4>
    <h5 class="movies" v-bind:class='isOld ? "old" : "New"'>Movies</h5>
    <button v-bind:id="bindit" disabled="disabled">button</button>
    <p :style="someStyles">Applied styles</p>

    <kbd v-if="num() == 0">Number is Even {{num()}}</kbd>
    <kbd v-else-if="num() == 1">Number is Odd {{num()}}</kbd>
    <kbd v-else>Not a Number</kbd>
  </div>
  <!-- <HelloWorld msg="Welcome to Your Vue.js App"/> -->
</template>

<script>
// import HelloWorld from './components/HelloWorld.vue'

export default {
  name: 'App',
  data(){
    return{
      name:"Anand",
      language:"Vue",
      content:`<kbd>Hello world</kbd>`,
      bindit:"Button",
      disabled:false,
      isOld:false,
      isNew:true,
      someStyles:{
        fontSize:48+"px",
        background:"smoke",
        color:"orangered",
        width:40+"px",
        margin:'auto'
      },
      num(){
        
      }
    }
  }
  // components: {
  //   HelloWorld
  // }
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

.movies{
  font-size:20px;
  width:80px;
  height:30px;
}

.old{
  background:black;
  color:white;
  
}

.New{
  background:orange;
  color:blue;
}


#Button{
  background:red;
  color:white;
  font-size:38px;
}
</style>
