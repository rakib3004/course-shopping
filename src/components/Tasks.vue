<template>
<header>
    <div :key="task.id" v-for="task in tasks">
    <Task @toggle-reminder="$emit('toggle-reminder', task.id)" @enroll-task="$emit('enroll-task', task.id)" @delete-task="$emit('delete-task',
     task)"  :task="task" />
    </div>
    </header>
</template>

<script>
import Task from './Task'


export default {
  name: 'Tasks',
  props:{
      task: Array,
  },
  components:{
      Task,
  },
  emits: ['delete-task','enroll-task', 'toggle-reminder'],
}
</script>
