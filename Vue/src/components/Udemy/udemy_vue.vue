<template>
  <div>
    <!-- <input type="text" v-on:input="getValue"> -->
    <h3>Click here to Learn Vue <a v-bind:href="vueLink">Vue</a> </h3>
    <input type="text" v-model="word">
    <button @click="displayValue" >Click</button>
    <ol>
      <li v-for="(item,index) in array" :key="index">{{item}}</li>
    </ol>
  </div>
  
</template>

<script>
export default {
  name:"Udemy_vue",

  data(){
    return {
      array:[],
      word:"",
      vueLink:"https://vuejs.org"
    }
  },

  methods : {
    // getValue(e){
    //   this.word = e.target.value
    // },
    displayValue()
    {
      this.array.push(this.word)
      this.word = ""
    }
  }


}
</script>

<style>

</style>