<template>
  <div>
    <!-- <input type="text" v-on:input="getValue($event)"> -->
    <h3>Click here to Learn Vue <a v-bind:href="vueLink">Vue</a></h3>
    <input type="text" v-model="word" v-on:keyup.enter="confirmName" />
    <!-- displayName only on enter key-->
    <button @click="displayValue">Click</button>
    <h2>{{ finalName }}</h2>
    <ol>
      <li v-for="(item, index) in array" :key="index">{{ item }}</li>
    </ol>
    <p v-html="htmlEle"></p>
    <kbd v-once style="font-size: 24px">Initial Count : {{ counter }}</kbd>
    <!--Update the value only once-->
    <br />
    <kbd style="font-size: 24px">Total Count : {{ counter }}</kbd>
    <div class="buttonBox">
      <!-- <button v-on:click="counter++">Add</button> -->
      <button @click.right="changeCount(2)">Add 2</button>
      <!--Only right click-->
      <button v-on:click.left="changeCount(-1)">Remove</button>
      <!--Only lerightft click-->
      <!-- <button v-on:click="counter = counter - 2">Remove 2</button> -->
    </div>
    <form action="" @submit.prevent="submitForm">
      <input type="text" placeholder="Form submission test" />
      <button>Submit</button>
    </form>
    <input type="text" placeholder="computed Properties" v-model="computed" />
    <h3>{{ addName }}</h3>

    <div class="Boxes">
      <div :style="box.a ? borderColor : normal" @click="boxSelected('A')">First</div>
      <div class="second" :class="{ boxB: box.b }" @click="boxSelected('B')">
        Second
      </div>
      <div :class="box.c ? 'boxC' : 'third'" @click="boxSelected('C')">Third</div>
      <div :class="changeStyle" @click="boxSelected('D')">Fourth</div>
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
      counter: 4,
      htmlEle: `<h4>Learn Vue</h4>`,
      finalName: "",
      computed: "",
      box: { a: false, b: false, c: false, d: false },
      borderColor: { borderColor: 'red', background: 'orange', color: 'white' },
      normal: { borderColor: 'grey', background: 'white', color: 'black' }
    };
  },
  computed: {
    addName() {
      return this.computed + " " + "Running";
    },
    changeStyle() {
      return this.box.d ? 'boxD' : 'third'
      // return this.box.d ? { boxD: this.box.d } : { third: !this.box.d }
    }
    // conditionCount(){
    //   if(this.counter > 20)
    //   {
    //      return this.counter = 0
    //   }
    //   else
    //   {
    //     return this.counter
    //   }
    // }
  },
  watch: {
    counter(newValue, old) {
      if (newValue > 20) {
        this.counter = 0;
      }
      console.log(old);
    },
  },

  methods: {
    // getValue(e){
    //   this.word = e.target.value
    // },
    confirmName() {
      this.finalName = this.word;
    },
    submitForm() {
      //event
      // event.preventDefault()
      alert("Hello");
    },
    displayValue() {
      this.array.push(`Total Count is ${this.counter}`);
      this.word = "";
    },
    changeCount(value) {
      this.counter += value;
    },
    boxSelected(selected) {
      if (selected == "A") {
        this.box = { a: true, b: false, c: false, d: false }
      }
      else if (selected == "B") {
        this.box = { a: false, b: true, c: false, d: false }
      }
      else if (selected == "C") {
        this.box = { a: false, b: false, c: true, d: false }
      }
      else if (selected == "D") {
        this.box = { a: false, b: false, c: false, d: true }
      }

    }

  },
};
</script>

<style>
.buttonBox {
  border: groove;
  display: flex;
  justify-content: space-between;
  width: 180px;
}

.Boxes {
  width: 800px;
  display: flex;
  justify-content: space-around;
  text-align: center;
  line-height: 80px;
}

.Boxes>* {
  width: 150px;
  border: 6px solid black;
  font-size: 20px;
  font-weight: 900;
}

.second,
.third,
.fourth {
  border-color: grey;
  background: white;
  color: black;
}

.boxB,
.boxC,
.boxD {
  border-color: red;
  background: orange;
  color: white;
}
</style>
