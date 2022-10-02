<script>
    import TodoItem from './TodoItem.vue'

    export default {
        components: { TodoItem },
        props: ['todos'],
        methods: {
            removeTodo(id) {
                this.$emit('removeTodo', id)
            }
        }
    }
</script>

<template>
    <ul class="list">
        <TodoItem 
            v-for="(todo, index) in todos" 
            :index="index"
            :key="todo.id" 
            :todo="todo"
            @removeTodo="removeTodo" 
        />
    </ul>
</template>