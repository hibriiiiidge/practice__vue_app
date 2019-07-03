<template>
  <button v-on:click="clicked_count++">
    You clicked {{ clicked_count }} times.
  </button>
</template>

<script>
export default {
  data () {
    return {
      clicked_count: 0
    }
  }
}
</script>