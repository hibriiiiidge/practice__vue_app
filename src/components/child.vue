<template>
  <div>
    child start
    <ul v-for="(value, key) in object" v-bind:key="value.id">
      <template v-if="key==='authors'">
        <li>
          {{ key }} :
          <template v-for="(author) in value">
            {{ author.name + ',' }}
          </template>
        </li>
      </template>
      <template v-else>
        <li> {{ key }} : {{ value }}</li>
      </template>
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