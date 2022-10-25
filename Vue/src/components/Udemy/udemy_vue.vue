<template>
  <div>
    <!-- <input type="text" v-on:input="getValue($event)"> -->
    <h3>Click here to Learn Vue <a v-bind:href="vueLink">Vue</a> </h3>
    <input type="text" v-model="word" v-on:keyup.enter="confirmName"> <!-- displayName only on enter key-->
    <button @click="displayValue">Click</button>
    <h2>{{finalName}}</h2>
    <ol>
      <li v-for="(item,index) in array" :key="index">{{item}}</li>
    </ol>
    <p v-html="htmlEle"></p>
    <kbd v-once style="font-size:24px;">Initial Count : {{counter}}</kbd> <!--Update the value only once-->
    <br>
    <kbd style="font-size:24px;">Total Count : {{counter}}</kbd>
    <div class="buttonBox">
      <!-- <button v-on:click="counter++">Add</button> -->
      <button v-on:click.right="changeCount(2)">Add 2</button> <!--Only right click-->
      <button v-on:click.left="changeCount(-1)">Remove</button> <!--Only lerightft click-->
      <!-- <button v-on:click="counter = counter - 2">Remove 2</button> -->
    </div>
      <form action="" v-on:submit.prevent="submitForm">
        <input type="text" placeholder="Form submission test">
        <button>Submit</button>
      </form>
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
      counter: 4,
      htmlEle: `<h4>Learn Vue</h4>`,
      finalName:""
    }
  },

  methods: {
    // getValue(e){
    //   this.word = e.target.value
    // },
    confirmName(){
      this.finalName = this.word
    },
    submitForm(){ //event
      // event.preventDefault()
      alert('Hello')
    },
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