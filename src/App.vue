<template>
  <div>
    <child :object="object"></child>
    <div> {{ message }} </div>
    <div v-bind:class="{ active: isActive }"> {{ message2 }} </div>
    <button v-on:click="reverse">Reverse</button>
    <div v-bind:class="[ { active: isActive }, errorClass]"></div>
    <count_button></count_button>
    <count_button></count_button>
    <count_button></count_button>
  </div>
</template>

<script>
import child from './components/child'
import count_button from './components/CountButton'

export default {
  components: {
    child,
    count_button
  },
  data () {
    return {
      message: 'Hello Vue!!',
      message2: '12345',
      isActive: 'active',
      errorClass: 'text-danger',
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
