<template>

<div class="container">

    <div>
        <p>{{ date }}</p>
        <h1>VueJs Tutorial ToDo List</h1>
        <p>{{ tasks.length }}</p>
    </div>
    <div>
        <NewToDo @newTask="addTask"></NewToDo>

        <ToDoList v-bind:tasks="tasks" @removeTask="removeTask"></ToDoList>
    </div>
</div>


</template>

<script type="text/javascript">


import NewToDo from './NewToDo.vue'
import ToDoList from './ToDoList.vue'

export default {
    name: "ToDoCard",

    components: {
        NewToDo,
        ToDoList
    },

    data() {

        return {
            day: ["Lundi", "Mardi", "Mercredi", "Jeudi", "Vendredi", "Samedi", "Dimanche"],
            month: ["Janvier", "Février", "Mars", "Avril", "Mai", "Juin", "Juillet", "Août", "Septembre", "Octobre", "Novembre", "Décembre"],
            tasks: [],
        }

    },
    computed: {

        date: function() {
            let today = new Date();
            let todate = `${this.day[(today.getDate())-1]}` + ' ' + today.getDay() + ' ' + `${this.month[(today.getMonth())]}` + ' ' + today.getFullYear()
            return todate
        }

    },

    methods: {
        addTask(task) {
            this.tasks.push({name: task, state: 0})
        },
        
        removeTask(task) {
            this.tasks.splice(task, 1)
        }
    }
}
</script>

<style scoped>

.container {
    width: 600px;
    min-height: 300px;
    background-color: #FFFFFF;
}

.container div:first-of-type {
    display: flex;
    justify-content: space-around;
    border-bottom: 1px solid rgb(236, 236, 236);
    box-shadow: 0px 0px 2px;

}

.container div:first-of-type h1 {
    color: #85D9C6;
    padding: 10px 0;
    font-weight: bold;
}

</style>