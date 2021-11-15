<template>
<header>
    <h1>Enrolling Courses: </h1>
    <div :key="task.id" v-for="task in tasks">
    <div v-if="task.isEnrolled==true">
    <Task @toggle-reminder="$emit('toggle-reminder', task.id)" @enroll-task="$emit('enroll-task', task.id)" @delete-task="$emit('delete-task',
     task)"  :task="task" />
     </div>
    </div>
    </header>
</template>

<script>
import Task from './Task'


export default {
  name: 'ShowTasks',
  props:{
      tasks: Array,
  },
  components:{
      Task,
  },
  emits: ['delete-task','enroll-task', 'toggle-reminder'],
}
</script>
