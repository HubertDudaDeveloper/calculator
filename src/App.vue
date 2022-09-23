<template>
  <div id="app">
    <CalcDisplay :display="display"/>
    <CalcButtons :button="button" @operation="operation"/>
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
      button: ['C', '+/-', '%', '/', 7, 8, 9, '*', 4, 5, 6, '-', 1, 2, 3, '+', 0, 0, '.', '='],
      display: ''
    }
  },
  methods: {
    operation (i) {
      switch (i) {
        case '=':
          this.equal()
          break
        case 'C':
          this.display = ''
          break
        case '%':
          this.equal()
          this.display = this.display / 100
          break
        case '+/-':
          this.display = this.display * -1
          break
        default:
          this.input(i)
      }
    },
    input (i) {
      this.display = this.display.toString()
      this.display = this.display.concat(i)
    },
    equal () {
      // eslint-disable-next-line
      this.display = eval(this.display)
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
