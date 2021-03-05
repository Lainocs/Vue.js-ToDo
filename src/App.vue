
<template>
  <div id="app">
     <ToDoCard></ToDoCard>
  </div>
</template>

<script>
import ToDoCard from './components/ToDoCard.vue'

export default {
  name: 'app',
  components: {
    ToDoCard,
  }
}
</script>

<style lang="css">

body {
  background-color: #F9D365;
  height: 100vh;
  width: 100vw;
  display: grid;
  place-items: center;
}

</style>