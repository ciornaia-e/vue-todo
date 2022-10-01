<script>
    export default {
        props: {
            todo: {
                type: Object,
                required: true
            }
        },
        methods: {
            onComplete() {
                this.todo.completed = !this.todo.completed
            },
            onRemove() {
                this.$emit('removeTodo', this.todo.id)
            }
        }
    }
</script>

<template>
    <li class="item">
        <div :class="{done: todo.completed}">
            <input @change="onComplete" type="checkbox" class="checkbox">
            <strong class="iterator">{{ todo.id }}</strong>
            <span>{{ todo.title }}</span>
        </div>
        <button @click="onRemove" class="remove">&times;</button>
    </li>
</template>