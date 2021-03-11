<template>
  <div class="row">
    <h1 class="col-md-4 col"> {{title}}</h1>
    <div class="col-md-6 col d-flex justify-content-left">
      <router-link to="/">Home</router-link> |
      <router-link to="/about">About</router-link>
    </div>
    <div class="col-md-2 col d-flex justify-content-left">
      <custom-button btn_width="150px" btn_text="Add task"/>
    </div>
  </div>
</template>

<script>
import CustomButton from "@/components/props/CustomButton";
export default {
  name: 'Header',
  props: {
    title: String,
  },
  components:{
    CustomButton,
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
h1{
  display: inline-block;
  background: red;
}
custom-button{
  display: inline-block;
}
</style>
