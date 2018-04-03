]<template>
  <div id="app">
    <ul>
      <todoItem
      v-for = "(task, index) in taskList"
      v-bind:key = "task.task"
      v-bind:taskData="task">
      </todoItem> 
    </ul>
    <form v-on:submit.prevent="addTask">
      <label for="">Add a new Task: <br></label>
      <input v-model="newTask" type="text">
      <input type="submit">
    </form>
  </div>
</template>

<script>
import todoItem from './components/to-doItem.vue';

export default {
  name: 'app',
  components: {
    todoItem
  },
  // data() function that returns an object, really important!
  data() {
    return {
      newTask: '',
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
        {
          done: false,
          task: "do more stuff"
        },
        {
          done: true,
          task: "don't forget this"
        }
      ]
    }
  },
  methods: {
    deleteItem(index) {
      this.taskList.splice(index, 1)
    },
    addTask() {
      // take the value at key newTask, passed in param
       // add the value of done as false
       let taskItem = {
        done: false,
        task: this.newTask
      }
      // add it to the taskList array
      this.taskList.push(taskItem);
      // clears the form
      this.newTask = '';
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
  text-decoration: line-through;
  color: green;
  display: inline;
}

</style>
