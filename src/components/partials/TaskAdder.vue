<template>
  <div class="modal" v-if="showModal">
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
  props:{
    showModal: Boolean
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
  .modal {
    position: fixed;
    top: 50%;
    left: 50%;
    transform: translate(-50%, -50%);
    width: 600px;
    max-width: 100%;
    height: 400px;
    max-height: 100%;
    background: #FFFFFF;
    box-shadow: 2px 2px 20px 1px;
    overflow-x: auto;
    display: flex;
    border-radius: 10px;
    flex-direction: column;
  }
</style>
