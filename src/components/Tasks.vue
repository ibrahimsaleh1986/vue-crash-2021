<template>
<div>
<div v-for="task in tasks" :key="task.id">
    <Task :task="task" @delete-task="deleteTask" @toggle-reminder="$emit('toggle-reminder',task.id)"/>
</div>
</div>
</template>

<script>
    import Task from "./Task.vue"
    export default{
        name:'Tasks',
        props:{
            tasks:Array
        },
        components:{
            Task
        },
       methods:{
           deleteTask(id)
           {
               this.$emit('delete-task',id)
           }
       }, 

    }
</script>