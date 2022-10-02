<script>
  import TodoList from './components/TodoList.vue'
  import AddTodo from './components/AddTodo.vue'
  
  export default {
    name: 'app',
    components: { TodoList, AddTodo },
    data() {
      return {
        todos: []
      }
    },
    methods: {
      removeTodo(id) {
        this.todos = this.todos.filter(index => index.id !== id)
      },
      addTodo(todo) {
        this.todos.push(todo)
      }
    },
    mounted() {
      fetch('https://jsonplaceholder.typicode.com/todos?_limit=3')
        .then(response => response.json())
        .then(json => this.todos = json)
    }
  }
</script>

<template>
  <div>
    <div class="wrapper">
      <div class="card">
        <h1 class="title">Todo application</h1>
        <AddTodo @addTodo="addTodo" />
        <TodoList :todos="todos" @removeTodo="removeTodo" />
      </div>
    </div>
  </div>
</template>
