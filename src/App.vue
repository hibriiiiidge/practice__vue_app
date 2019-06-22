<template>
  <div>
    <child :object="object"></child>
    <div> {{ message }} </div>
    <div v-bind:class="{ active: isActive }"> {{ message2 }} </div>
    <button v-on:click="reverse">Reverse</button>
  </div>
</template>

<script>
import child from './components/child'

export default {
  components: {
    child
  },
  data () {
    return {
      message: 'Hello Vue!!',
      message2: '12345',
      isActive: false,
      object: {
        title: 'How to do lists in Vue',
        author: 'Jane Doe',
        publishedAt: '2016-04-10'
      }
    }
  },
  methods: {
    reverse: function() {
      this.message2 = this.message2.split("").reverse().join("");
    }
  }
}
</script>
