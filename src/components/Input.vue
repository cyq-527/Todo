<template>
  <div>
    <input type="text" v-model="value" >
    <input type="submit" @click="submit">
    <ul v-for="(a,index) in list" v-bind:key="index">
      <li>{{a}}</li>
    </ul>
  </div>
</template>

<script>
export default {
  name: 'Inp',
  data(){
    return {
      value:'',
      list:[]
    }
  },
  methods:{
    submit(){
      this.list.push(this.value);
      this.value=''
    }
  }
}
</script>

<style scoped>

</style>
