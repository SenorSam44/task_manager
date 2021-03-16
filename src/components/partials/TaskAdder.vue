<template>
  <div class="modal" v-if="showModal">
    <form @submit="onSubmit" class="add-form">
      <div class="form-control">
        <label for="name">Task name </label>
          <input type="text" v-model="name" placeholder="Task Name" id="name" name="name"/>

      </div>
      <div class="form-control">
        <label for="date">Date</label>
          <input type="date" v-model="date" placeholder="Task Date" name="date" id="date"/>

      </div>
      <div class="form-control">
        <label style="padding: 10px" for="reminder">Set Reminder
          <input style="display: inline-block; width: auto" type="checkbox" v-model="reminder" id="reminder" name="reminder"/>
        </label>
      </div>

      <button class="btn btn-primary" type="submit">Submit</button>
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
    display: block;
  }
  .modal {
    position: fixed;
    top: 50%;
    left: 50%;
    transform: translate(-50%, -50%);
    width: 600px;
    max-width: 100%;
    height: max-content;
    max-height: 100%;
    background: #FFFFFF;
    box-shadow: 2px 2px 20px 1px;
    overflow-x: auto;
    display: flex;
    border-radius: 10px;
    flex-direction: column;
  }

  .form-control{
    margin: 10px;
  }
  .form-control label{
    display: block;
    width: 100%;
    text-align: left;
    padding-bottom: 10px;
  }
  .form-control input{
    display: block;
    width: 100%;
  }

  button{
    display: flex;
    float: right;
    margin-top: 15px;
    margin-right: 15px;
  }
</style>
