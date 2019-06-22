<template>
  <div>
    <child :groceryList="groceryList"></child>
    <div> {{ message }} </div>
    <div> {{ message2 }} </div>
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
      groceryList: [
        { id: 0, text: 'Vegetables' },
        { id: 1, text: 'Cheese' },
        { id: 2, text: 'Whatever else humans are supposed to eat' }
      ]
    }
  },
  methods: {
    reverse: function() {
      this.message2 = this.message2.split("").reverse().join("");
    }
  }
}
</script>
