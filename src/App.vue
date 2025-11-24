<template>
  <div>
    <div>
      <h1>Counter</h1>
      <button v-on:click="increment">
        {{count}}
      </button>
    </div>
    <div>
      <h1>{{title}}</h1>
      <input type="text" v-model="inputText">
      <button v-on:click="onClick">Add</button>
      <TodoItem
        v-for="(task, key) in tasks"
        :task="task"
        :key="key"
        @delete-task="deleteTask"></TodoItem>
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
import TodoItem from './components/ToDoItem.vue'
export default {
  components: {
        TodoItem
  },
  data: () => ({
    count: 0,
    title: "To Do Appli",
    inputText: "",
    tasks: [],
    is_checked: false,
  }),
  methods: {
    increment: function(){
      this.count++
    },
    onClick: function(){
      this.message = this.inputText
      this.tasks.push(this.inputText)
    },
    deleteTask: function(taskToDelete){
      const index = this.tasks.indexOf(taskToDelete)
      if(index !== -1){
        this.tasks.splice(index, 1)
      }
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

