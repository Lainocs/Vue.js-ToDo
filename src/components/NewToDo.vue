<template>
    <div id="ntd">
        <input type="text" v-model="task">
        <button v-on:click="sendTask(task)">Valider</button>
    </div>
</template>

<script type="text/javascript">

export default {
    el: "#ntd",

    name: "NewToDo",

    methods: {
        sendTask: function(task) {
            if(task != "") {
                this.$emit('newTask', this.task)
            } else {
                alert('rien')
            }
        }
    },
    
    data() {
        return {
            task: " ",
        }
    }

}

</script>

<style scoped>

</style>