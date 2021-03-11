<template>
  <div class="home">
    <task-adder msg="Welcome to Your Vue.js App"/>
  </div>
</template>

<script>
// @ is an alias to /src
import TaskAdder from '@/components/partials/TaskAdder.vue'

export default {
  name: 'Home',
  components: {
    TaskAdder
  }
}
</script>
