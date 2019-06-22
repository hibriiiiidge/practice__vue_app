<template>
  <div>
    <child :groceryList="groceryList"></child>
    <div> {{ message }} </div>
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
      groceryList: [
        { id: 0, text: 'Vegetables' },
        { id: 1, text: 'Cheese' },
        { id: 2, text: 'Whatever else humans are supposed to eat' }
      ]
    }
  }
}
</script>
