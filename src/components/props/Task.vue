<template>
  <div @dblclick="$emit('toggle-reminder', task.id)" :class="[task.reminder ? 'task-reminder': '', 'task']">
    <i @click="$emit('delete-task',task.id)" class="fas fa-times"></i>
    <h3>
      {{task.name}}
    </h3>
    <p> {{task.date}}</p>
  </div>
</template>

<script>
export default {
  name: 'Task',
  props: {
    task: Object,
  },
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
  .task{
    background: antiquewhite;
    padding: 5px;
    margin: 10px;
    cursor: pointer;
  }

  .task-reminder{
    border-left: 5px solid #42b983;
  }
  .task h3{
    display: flex;
    align-items: center;
    justify-content: space-between;
    padding: 10px;
    text-transform: capitalize;
  }

  .task i{
    display: block;
    float: right;
    padding: 10px;
    color: red;
  }
</style>
