<template>
  <button :style="{width: btn_width}" class="btn" @click="addTask()">{{btn_text}}</button>
</template>

<script>
export default {
  name: 'Header',
  props: {
    btn_text: {
      type: String,
      default: 'Submit'
    },
    btn_width:{
      type: String,
      default: '80px'
    },
  }, methods:{
    addTask(){

    }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
  button{
    padding: 10px;
    margin: 10px;
    background: #42b983;
  }
</style>
