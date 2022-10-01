<script>
    export default {
        methods: {
            data() {
                return {
                    title: ''
                }
            },
            onSubmit() {
                if (this.title.trim()) {
                    const newTodo = {
                        id: Date.now(),
                        title: this.title,
                        completed: false
                    }

                    this.$emit('addTodo', newTodo)
                    this.title = ''
                }
            }
        }
    }
</script>

<template>
    <form @submit.prevent="onSubmit" class="form">
        <input v-model="title" type="text" class="input">
        <button type="submit">Create</button>
    </form>
</template>