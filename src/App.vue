<template>
  <div id="app">
    <input type="text" v-model="value">
    <button @click="submit">submit</button>
    <ul>
      <todo-item @delete="hanldeDelete" v-for="(item,index) in list" :key="index" :content="item" :index="index"></todo-item>
    </ul>
  </div>
</template>

<script>
import todoItem from './components/TodoItem'
export default {
  name: 'app',
  data(){
    return{
      list:[],
      value:''
    }
  },
  components:{
     'todo-item':todoItem
  },
  methods:{
    submit()
    {
      this.list.push(this.value);
      this.value=''
    },
    hanldeDelete(index)
    {
      this.list.splice(index,1)
    }
  }

}
</script>

<style>
</style>
