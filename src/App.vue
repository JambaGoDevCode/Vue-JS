<template>
  <img alt="Vue logo" src="./assets/logo.png">
  <RecipeItem />
</template>

<script>
import RecipeItem from './components/RecipeItem.vue'

export default {
  name: 'App',
  components: {
    RecipeItem
  }
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
