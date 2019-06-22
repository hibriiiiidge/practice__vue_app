<template>
  <div>
    child start
    <ul v-for="todo in groceryList">
      <li>
        {{ todo.id }}: {{ todo.text }}
      </li>
    </ul>
    child end
  </div>
</template>

<script>
export default {
  props: ['groceryList']
}
</script>