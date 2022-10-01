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
            v-for="todo in todos" 
            :key="todo.id" 
            :todo="todo"
            @removeTodo="removeTodo" 
        />
    </ul>
</template>