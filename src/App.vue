<template>
  <div id="app">
    <Kanban :data="data"/>
  
  </div>
</template>

<script>
import Kanban from "./components/Kanban.vue";

export default {
  name: "App",
  components: {
    Kanban,
  },
  data(){
    return{
      data:[
        {
          name:"todo",
          color:"#E0BBE4",
          tasks:[]
        },
         {
          name:"doing",
          color:"#FEC8D8",
          tasks:[]
        },
         {
          name:"done",
          color:"#FFBFA6",
          tasks:[]
        }
      ]
    }
  }
};
</script>

<style>
#app {
  height: 100vh;
}
</style>
