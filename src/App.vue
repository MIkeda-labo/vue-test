<template>
  <div>
    <div>
      <h1>Counter</h1>
      <button v-on:click="increment">
        {{count}}
      </button>
    </div>

  </div>
</template>

<!--  //Composition APIの書き方
<script setup>
import { ref } from 'vue'

const count = ref(0)

function increment(){
  count.value++
}
</script>     -->

<script>
export default {
  data: () => ({
    count: 0,
  }),
  methods: {
    increment: function(){
      this.count++
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

