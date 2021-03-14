<template>
 <div :key="task.id" v-for="task in tasks">
   <task @toggle-reminder="$emit('toggle-reminder', task.id)" @delete-task="$emit('delete-task', task.id)" :task="task"/>
 </div>
</template>

<script>
import Task from "@/components/props/Task";
export default {
  name: 'TaskViewer',
  components: {Task},
  props: {
    tasks: Array
  },
  emits: ['delete-task', 'toggle-reminder']

}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
h3 {
  margin: 40px 0 0;
}
ul {
  list-style-type: none;
  padding: 0;
}
li {
  display: inline-block;
  margin: 0 10px;
}
a {
  color: #42b983;
}
</style>
