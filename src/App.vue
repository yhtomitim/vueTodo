<template>
  <div id="app">
    <ul>
      <li v-for = "(task, index) in taskList" v-bind:key = "task.task">
        <p class="inline" v-bind:class="{done : task.done}">{{task.task}}</p>
        <input v-model="task.done" type="checkbox">
        <button v-on:click="deleteItem(index)">Finished</button>
      </li> 
    </ul>
  </div>
</template>

<script>

export default {
  name: 'app',
  data() {
    return {
      taskList: [
        {
          done: false,
          task: 'Build a Vue App'
        },
        {
          done: false,
          task: 'Components!'
        },
        {
          done: false,
          task: "add in Async"
        },
      ]
    }
  },
  methods: {
    deleteItem(index) {
      this.taskList.splice(index, 1)
    }
  }
}
</script>

<style>
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}

ul {
  list-style: none;
}

.inline {
  display: inline;
}

.done {
  /* text-decoration: line-through; */
  color: green;
  display: inline;
}

</style>
