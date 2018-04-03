<template>
  <li id="todoItem">
    <p class="inline" v-bind:class="{done : taskData.done}">{{taskData.task}}</p>
    <input v-model="taskData.done" type="checkbox">
    <button v-on:click="deleteItem(index)">Finished!</button>
  </li> 
</template>

<script>
export default {
  name: 'todoItem',
  props: ['taskData', 'index']  
}
</script>

<style scoped>

</style>


