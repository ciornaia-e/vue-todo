<script>
  import { RouterLink, RouterView } from 'vue-router'
  import TodoList from './components/TodoList.vue'
  import AddTodo from './components/AddTodo.vue'
  
  export default {
    name: 'app',
    components: { TodoList, AddTodo },
    data() {
      return {
        todos: [
          {id: 1, title: 'Todo bread', completed: false},
          {id: 2, title: 'Todo milk', completed: false},
          {id: 3, title: 'Todo fruits', completed: false}
        ]
      }
    },
    methods: {
      removeTodo(id) {
        this.todos = this.todos.filter(index => index.id !== id)
      },
      addTodo(todo) {
        this.todos.push(todo)
      }
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
        <!-- <nav>
          <RouterLink to="/">Home</RouterLink>
          <RouterLink to="/about">About</RouterLink>
        </nav> -->
    </div>

    <!-- <RouterView /> -->
  </div>
</template>
