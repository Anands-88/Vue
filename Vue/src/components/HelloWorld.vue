<template>
  <div>
    <h1>{{name}}</h1>
    <h2 v-text="language"></h2>
    <h3 v-html="content"></h3>
    <h4>{{num()}}{{bindit}}</h4>
    <h5 class="movies" v-bind:class='isOld ? "old" : "New"'>Movies</h5>
    <button v-bind:id="bindit" disabled="disabled">button</button>
    <p :style="someStyles">Applied styles</p>

    <kbd v-if="num() == 0">Nuv-for="(item,index) in array" :key="index"mber is Even {{num()}}</kbd>
    <kbd v-else-if="num() == 1">Number is Odd {{num()}}</kbd>
    <kbd v-else>Not a Number</kbd>

    <strong v-show="isNew">V-show</strong>
    <h3 v-for="(num,index) in array" v-bind:key="index">{{num}}</h3>

    <p>Conditional Rendering in list</p>
    <template v-for="num in array" :key="num">
      <h2 v-if="num%2==0">{{num}}</h2>
    </template>

    <template v-for="numb in array" :key="numb">
      <h2>Methods in vue {{multiply(numb)}} {{num(numb)}}</h2>
    </template>
  </div>
  
</template>

<script>


export default {
  name: 'HelloWorld',
  data(){
    return{
      name:"Anand",
      language:"Vue",
      content:`<kbd>Hello world</kbd>`,
      bindit:"Button",
      disabled:false,
      isOld:false,
      isNew:false,
      someStyles:{
        fontSize:48+"px",
        background:"smoke",
        color:"orangered",
        width:40+"px",
        margin:'auto'
      },
      num(a){
        let res = a+a
        if(res.toString().length == 1)
        {
          return "0"+res
        }
        return res
      },
      array:[1,2,3,4,5,6,7,8,9]
    }
  },
  methods:{
    multiply(a){
      let res = a*a
      if(res.toString().length == 1)
      {
        return "0"+res
      }
      return res
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
