<template>
    <div v-for="task in tasks" :key="task.id">
        <!--Catch emit from Task child vuel leve 3 . 
        You pass emit her @delete-task="$emit('delete-task',task.id)"-->
        <Task  @toggle-reminder = "$emit('toggle-reminder', task.id)" 
        @delete-task="$emit('delete-task',task.id)" :task="task" />
    </div>
</template>
<script>
import Task from './Task.vue';

export default {
   name: 'Tasks',
   props: {
    tasks: Array
   },
   components: {
    Task
   },

   emits: ['delete-task','toggle-reminder']
}
</script>