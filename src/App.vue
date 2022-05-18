<template>
  <div class="home">
    <h1>Aplikacja z zadaniami</h1>
    <ToDoApp />
  </div>
</template>

<script>
import Todo from './components/ToDoApp.vue'

export default {
  components: {
    ToDoApp: Todo
  }
}

</script>

<style>

@font-face {
  font-family: myFont;
  src: url('fonts/Oxanium-VariableFont_wght.ttf');
} 

.home{
  font-family: myFont;
}

</style>