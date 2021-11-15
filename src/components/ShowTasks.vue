<template>
<header>
    <h1>Enrolling Courses: </h1>
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
      tasks: Array,
  },
  components:{
      Task,
  },
  emits: ['delete-task','enroll-task', 'toggle-reminder'],
}
</script>
