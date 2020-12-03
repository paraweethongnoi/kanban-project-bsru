<template>
  <div id="app">
    <Kanban :data="data" :create_tesk_submin=" create_tesk_submin"/>
  
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
          tasks:[
            {
              tasks_name:"test"
            }
          ]
        },
         {
          name:"doing",
          color:"#FEC8D8",
          tasks:[ {
              tasks_name:"test"
            }]
        },
         {
          name:"done",
          color:"#FFBFA6",
          tasks:[ {
              tasks_name:"test"
            }]
        }
      ]
    }
  },
  methods:{
    create_tesk_submin(column_index,item){
      this.data[column_index].tasks.push(item)
      
    }
  }

};
</script>

<style>
#app {
  height: 100vh;
}
</style>
