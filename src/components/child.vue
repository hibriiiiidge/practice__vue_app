<template>
  <div>
    child start
    <ul v-for="(grocery, index) in groceryList" :key='index'>
      <li>
        {{ grocery.id }}: {{ grocery.text }}
      </li>
    </ul>
    child end
  </div>
</template>

<script>
export default {
  props: ['groceryList'],
  created: function() {
    this.$parent.message = 'Change parent message!!'
  }
}
</script>