<template>
  <div id="app">
    <AnimalsList></AnimalsList>
    <h1>Extras</h1>
    <ButtonDisabledAfter></ButtonDisabledAfter>
    <ButtonConfirm />
  </div>
</template>

<script>
import AnimalsList from './components/AnimalsList.vue'
import ButtonDisabledAfter from './components/ButtonDisabledAfter.vue'
import ButtonConfirm from './components/ButtonConfirm.vue'

export default {
  name: 'app',
  components: {
    AnimalsList,
    ButtonDisabledAfter,
    ButtonConfirm
  }
}
</script>

<style>
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
