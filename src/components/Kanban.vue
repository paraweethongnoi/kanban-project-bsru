<template>
  <div class="Kanban">
      Kanban 
      <div class="column" :style="{backgroundColor:column.color}" v-for="(column , index) in data" :key="index">
  <div class="column-header">
      {{column.name}}
  </div>

  <div class="column-body">
    <div class="create-task" @click="create_task(index)">
      Create Task
    </div>
  </div>
  </div>
  <b-modal ref="create-task-modal"  title="Create Task">
    <p class="my-4">Hello from modal!</p>
    </b-modal>
  </div>
</template>

<script>
export default {
    props:{
        data:Array
    },
    methods:{
        create_task(index_column){
            console.log(index_column);
            this.$refs["create-task-modal"].show()
        }
    }
};
</script>

<style>
.Kanban{
    width: 100%;
    height: 100%;
    background-color: teal;
}
.column{
    height: 600px;
    width: 300px;
    border-radius:10px;
    display: inline-block;
    margin: 25px;
    padding: 15px;
    -webkit-box-shadow: 10px 10px 18px -15px rgba(255,255,255,1);
-moz-box-shadow: 10px 10px 18px -15px rgba(255,255,255,1);
box-shadow: 10px 10px 18px -15px rgba(255,255,255,1);
}
.column-header{
    display: flex;
    align-items: center;
    justify-content: center;
    height: 50px;
    font-size: 32px;
    font-weight: bold;
}
.column-body{
    height: calc(100% - 50px);
    border-radius: 10px;
    padding: 5px;
    background-color: rgba(240, 248, 255, 0.534);
}
.create-task{
    width: 100;
    height: auto;
    padding: 10px;
    border-radius: 5px;
    background-color: rgb(245, 135, 152);
    cursor: pointer;
}
.create-task:hover{
    background-color: rgba(233, 150, 122, 0.678);
}
</style>