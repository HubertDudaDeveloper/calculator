<template>
    <div class="container">
      <button v-for="(item, index) in button" :key="index" class="button" @click="click(item)">
        {{ item }}
      </button>
    </div>
</template>
<script>
import Vue from 'vue'
export default Vue.extend({
  name: 'CalcButtons',
  props: {
    button: String
  },
  methods: {
    click (item) {
      this.$emit('operation', item)
    }
  }
})
</script>
<style>
.container {
  height: 75%;
  border-radius: 0px 0px 25px 25px;
  display: grid;
  grid-template-columns: repeat(4, 1fr);
  grid-template-rows: repeat(5, 1fr);
  gap: 10px;
}
.button {
  border: 0px solid grey;
  background-color: rgba(255, 255, 255, 0.186);
  border-radius: 100%;
  box-shadow: 10px 10px 10px lightgray;
}
</style>
