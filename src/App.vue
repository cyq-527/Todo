<template>
  <div id="app">
    <input-item @addItem="addItem"></input-item>
    <todo-item  :list="todolist" @addDone="addDone" :title="title[0]"></todo-item>
    <todo-item  :list="donelist" :list-type="true"  :title="title[1]" ></todo-item>
  </div>
</template>

<script>
  import InputItem from './components/InputItem'
import TodoItem from './components/TodoItem'
export default {
  name: 'app',
  data(){
    return{
      title:['todo','done'],
      todolist:[],
      donelist:[]
    }
  },
  components:{
     'todo-item':TodoItem,
    'input-item':InputItem
  },
  methods:{
    addItem(value)
    {
      this.todolist.push(value)
    },
    addDone(index)
    {
      this.donelist.push(this.todolist.splice(index,1)[0])
    },
    delete(index)
    {
      this.donelist.splice(index,1)
    }

  }

}
</script>

<style>
  *{
    padding: 0;
    margin: 0;
  }
</style>
