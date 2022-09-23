<template>
  <div id="app">
    <CalcDisplay />
    <CalcButtons :button="button"/>
  </div>
</template>

<script lang="ts">
import Vue from 'vue'
import CalcDisplay from './components/CalcDisplay.vue'
import CalcButtons from './components/CalcButtons.vue'

export default Vue.extend({
  name: 'App',
  components: {
    CalcDisplay,
    CalcButtons
  },
  data () {
    return {
      button: [1, 2, 3, 4, 5, 6, 7, 8, 9, 0]
    }
  }
})
</script>

<style lang="scss">
body {
  display: flex;
  justify-content: center;
}
#app {
width: 320px;
min-height: 50vh;
border-radius: 25px;
box-shadow: 1px 1px 10px lightgray;
}
</style>
