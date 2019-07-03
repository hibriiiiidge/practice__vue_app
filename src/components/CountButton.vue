<template>
  <button v-on:click="clicked_count++" v-bind:style="styleObject">
    You clicked {{ clicked_count }} times.
  </button>
</template>

<script>
export default {
  data () {
  // data: function () {
    return {
      clicked_count: 0,
      styleObject: {
        color: 'red',
        fontSize: '13px'
      }
    }
  }
}
</script>