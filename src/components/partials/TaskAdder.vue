<template>
  <div>
    <form @submit="onSubmit" class="add-form">
      <div class="form-control">
        <label>Task name
          <input type="text" v-model="name" placeholder="Task Name" name="name"/>
        </label>
      </div>
      <div class="form-control">
        <label>Date
          <input type="date" v-model="date" placeholder="Task Date" name="date"/>
        </label>
      </div>
      <div class="form-control">
        <label>Set Reminder
          <input type="checkbox" v-model="reminder" name="reminder"/>
        </label>
      </div>

      <button type="submit">Submit</button>
    </form>
  </div>
</template>

<script>
export default {
  name: 'TaskAdder',
  data(){
    return{
      name:'',
      date: '',
      reminder: false,
    }
  },
  methods: {
    onSubmit(e){
      e.preventDefault()

      if(!this.name) {
        alert("please add a task name");
      }
      const newTask ={
        id: Math.floor(Math.random()),
        name: this.name,
        date: this.date,
        reminder: this.reminder,
      }
      this.$emit('add-task',newTask)
      this.name= "";
      this.date= "";
      this.reminder= false;

    }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
  .add-form{
    margin: 20px;
  }
</style>
