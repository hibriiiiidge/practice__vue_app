<template>
  <div>
    <ol>
      <li v-for="todo in todos">
        {{ todo.text }}
      </li>
    </ol>
  </div>
</template>

<script>
export default {
  data () {
    return {
      todos: [
        { text: 'hoge' },
        { text: 'hoge2' },
        { text: 'hoge3' },
      ]
    }
  }
}
</script>
