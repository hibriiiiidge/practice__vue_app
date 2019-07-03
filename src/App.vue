<template>
  <div>
    <child :object="object"></child>
    <div> {{ message }} </div>
    <div v-bind:class="{ active: isActive }"> {{ message2 }} </div>
    <button v-on:click="reverse">Reverse</button>
    <div class="static" v-bind:class="classObject"></div>
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
      isActive: true,
      error: {
        type: 'fatal',
      },
      object: {
        title: 'How to do lists in Vue',
        author: 'Jane Doe',
        publishedAt: '2016-04-10'
      }
    }
  },
  computed: {
    classObject: function () {
      return {
        active: this.isActive && !this.error,
        'text-danger': this.error && this.error.type === 'fatal'
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
