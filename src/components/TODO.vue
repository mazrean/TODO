<template>
  <div>
      <div>TODO</div>
      <div class="List Compreted">
        <h1>完了済み</h1>
        <div v-for="Task in Tasks" :key="Task.Title">
            <div v-if="Task.State==true" class="Task">{{Task.Title}}</div>
        </div>
      </div>
      <div class="List Uncompreted">
        <h1>未完</h1>
        <div v-for="Task in Tasks" :key="Task.Title">
            <div v-if="Task.State==false" class="Task">{{Task.Title}}</div>
        </div>
      </div>
      <div class="Input">
         <label for>
            タイトル
            <input type="text" v-model="TaskTitle">
         </label>
         <button @click="AddTask">add</button>
         <button @click="CompreteTask">Compreted</button>
      </div>
  </div>
</template>

<script>
export default {
  name: "TODO",
  data(){
      return{
          Tasks:[],
          TaskTitle:"",
      }
  },
  methods:{
      AddTask(){
          let b=true;
          for(let i=0;i<this.Tasks.length;i++){
              if(this.Tasks[i].Title==this.TaskTitle){
                  b=false;
              }
          }
          if(b==true){
              this.Tasks.push({Title:this.TaskTitle,State:false});
          }
          this.TaskTitle=""
      },
      CompreteTask(){
          for(let i=0;i<this.Tasks.length;i++){
              if(this.Tasks[i].Title==this.TaskTitle){
                  this.Tasks[i].State=true;
              }
          }
          this.TaskTitle=""
      }
  }
};
</script>

<style>
.List{
    width:45%;
    color:white;
    float: left;
}
.Compreted{
    background-color: blue;
}
.Uncompreted{
    background-color: red;
}
.Input{
    float: right;
}
</style>