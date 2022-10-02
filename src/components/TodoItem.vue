<script>
    export default {
        props: {
            todo: {
                type: Object,
                required: true
            },
            index: Number
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
            <strong class="iterator">{{ index + 1 }}</strong>
            <span>{{ todo.title }}</span>
        </div>
        <button @click="onRemove" class="remove">&times;</button>
    </li>
</template>