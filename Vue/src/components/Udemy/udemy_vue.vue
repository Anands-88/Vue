<template>
  <div>
    <!-- <input type="text" v-on:input="getValue($event)"> -->
    <h3>Click here to Learn Vue <a v-bind:href="vueLink">Vue</a> </h3>
    <input type="text" v-model="word">
    <button @click="displayValue">Click</button>
    <ol>
      <li v-for="(item,index) in array" :key="index">{{item}}</li>
    </ol>
    <p v-html="htmlEle"></p>
    <kbd style="font-size:24px;">Total Count : {{counter}}</kbd>
    <div class="buttonBox">
      <!-- <button v-on:click="counter++">Add</button> -->
      <button v-on:click="changeCount(2)">Add 2</button>
      <button v-on:click="changeCount(-1)">Remove</button>
      <!-- <button v-on:click="counter = counter - 2">Remove 2</button> -->
    </div>
  </div>

</template>

<script>
export default {
  name: "Udemy_vue",

  data() {
    return {
      array: [],
      word: "",
      vueLink: "https://vuejs.org",
      counter: 0,
      htmlEle: `<h4>Learn Vue</h4>`,
    }
  },

  methods: {
    // getValue(e){
    //   this.word = e.target.value
    // },
    displayValue() {
      this.array.push(`Total Count is ${this.counter}`)
      this.word = ""
    },
    changeCount(value) {
      this.counter += value
    }
  }


}
</script>

<style>
.buttonBox {
  border: groove;
  display: flex;
  justify-content: space-between;
  width: 180px;
}
</style>