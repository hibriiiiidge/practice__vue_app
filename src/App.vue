<template>
  <div>
    {{ message }}
    <button v-on:click="cMessage">Click</button>
  </div>
</template>

<script>
export default {
  data () {
    return {
      message: 'Hello Vue.js!'
    }
  },
  methods: {
    cMessage: function () {
      this.message = this.message.split('').reverse().join('')
    }
  }
}
</script>
