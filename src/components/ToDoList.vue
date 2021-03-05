<template>
    <div class="tasks">
        <div class="task" :key="task" v-for="task in tasks">
            <input type="checkbox">
            <label>{{ task.name }}</label>
            <button @click="removeTask(tasks.indexOf(task))" class="button is-danger"></button>
        </div>
    </div>
</template>

<script>
export default {
    name: 'ToDoList',
    props: {
        tasks: {
            type: Array,
            default: () => []
        },
        name: {
            type: String
        }
    },
    
    methods: {
        removeTask(task) {
            this.$emit('removeTask', task)
        }
    }
}
</script>

<style>

.task {
    display: flex;
    justify-content: space-around;
    align-items: center;
}

</style>