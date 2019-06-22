<template>
  <div>
    child start
    <ul v-for="value in object">
      <li>
        {{ value }}
      </li>
    </ul>
    child end
  </div>
</template>

<script>
export default {
  props: ['object'],
  created: function() {
    this.$parent.message = 'Change parent message!!'
  }
}
</script>