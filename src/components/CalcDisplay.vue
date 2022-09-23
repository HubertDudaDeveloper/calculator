<template>
    <div class="display">
        {{ display }}
    </div>
</template>
<script>
import Vue from 'vue'
export default Vue.extend({
  name: 'CalcDisplay',
  props: {
    display: String
  }
})
</script>
<style>
.display {
    box-sizing: border-box;
    display: flex;
    justify-content: end;
    align-items: center;
    height: 25%;
    box-shadow: 1px 1px 10px lightgray;
    border-radius: 25px 25px 0px 0px;
    font-size: 2.5em;
    padding: 20px;
}
</style>
