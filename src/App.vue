<template>
  <Header title="Task Manager"/>
  <div class="container">
    <router-view/>
  </div>
</template>

<script>
  import Header from "@/components/partials/Header";

  export default {
    name: 'App',
    components:{
      Header,
    },
    data(){
      return{
        tasks: []
      }
    }, created() {
      this.tasks=[
        {
          id: 1,
          text: "oijfad",
          day: 'dfsa',
          reminder: true
        },
        {
          id: 2,
          text: "oijfad",
          day: 'dfsa',
          reminder: true
        },
        {
          id: 3,
          text: "oijfad",
          day: 'dfsa',
          reminder: false
        },
      ]
    }
  }
</script>
<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
}

#nav {
  padding: 30px;
}

#nav a {
  font-weight: bold;
  color: #2c3e50;
}

#nav a.router-link-exact-active {
  color: #42b983;
}
</style>
