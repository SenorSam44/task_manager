<template>
  <div class="home">
<!--    <task-adder @add-task="addTask"/>-->
  </div>
  <task-viewer @toggle-reminder="toggleReminder" @delete-task="deleteTask" :tasks="tasks"/>
</template>

<script>
// @ is an alias to /src
import TaskViewer from "@/components/partials/TaskViewer";

export default {
  name: 'Home',
  components: {
    TaskViewer
  },
  data(){
    return{
      tasks: []
    }
  },
  methods:{
    deleteTask(id){
      if (confirm("Are you sure?")){
        this.tasks = this.tasks.filter((task) =>
            task.id !== id
        )}
    },
    toggleReminder(id){
      console.log(id);
      this.tasks = this.tasks.map((task)=> task.id ===id? {...task, reminder: !task.reminder} :task)
    },

  },
  created() {
    this.tasks=[
      {
        id: 1,
        name: "task 1",
        date: "13 februray, 2021",
        reminder: true

      },
      {
        id: 2,
        name: "task 2",
        date: "14 februray, 2021",
        reminder: true

      },
      {
        id: 3,
        name: "Order cloths",
        date: "13 februray, 2021",
        reminder: false

      },
      {
        id: 4,
        name: "Prepare Food",
        date: "15 februray, 2021",
        reminder: true

      }
    ]
  }
}
</script>
