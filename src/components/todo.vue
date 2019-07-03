<template>
  <div>
    <form v-on:submit.prevent='addNewTodo'>
      <label>Add a todo</label>
      <input v-model='newTodoText'>
      <button>Add</button>
    </form>
    <ul>
      <li is="todo_item" v-for="(todo, index) in todos" v-bind:key="todo.id" v-bind:title="todo.title" v-on:remove="todos.splice(index, 1)"></li>
    </ul>
  </div>
</template>

<script>
import todo_item from './todo/todoItem'

export default {
  components: {
    todo_item
  },
  data(){
    return {
      todos: [
        { id: 1, title: 'oooo'},
        { id: 2, title: 'aaaa'},
        { id: 3, title: 'iiii'},
      ],
      newTodoText: '',
      nextId: 4
    }
  },
  methods: {
    addNewTodo: function() {
      this.todos.push({
        id: this.nextId++,
        title: this.newTodoText,
      })
      this.newTodoText = ''
    }
  }
}
</script>