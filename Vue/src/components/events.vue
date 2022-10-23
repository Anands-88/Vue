
<template>
    <div>
        <input type="text" name="" id="" v-on:change="inputValue">
        <button v-on:click="getValue">Click</button>
        <h1>{{values}}</h1>
    </div>
    <div>
        <h2>Count : {{count}}</h2>
        <button v-on:click="increment()">Increment</button>
        <button @click="decrement">Decrement</button>
    </div>
</template>
<script>
    export default{
        name:"EventPage",
        data(){
            return {
                count:0,
                values:""
            }
        },
        methods:{
            inputValue(event){
                this.values = event.target.value;
            },
            getValue(){
                return this.values
            },
            increment(){
                this.count+=1
            },
            decrement(){
                this.count-=1
            }
        }
    }
</script>
<style></style>