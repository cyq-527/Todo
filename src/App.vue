<template>
  <div id="app">
    <inp></inp>
    <list></list>
  </div>
</template>

<script>
import Inp from './components/Input'
import List from './components/List'
export default {
  name: 'app',
  components: {
    Inp,
    List
  }
}
</script>

<style>
#app {
}
</style>
