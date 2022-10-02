<script>
    export default {
        data() {
            return {
                title: ''
            }
        },
        methods: {
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