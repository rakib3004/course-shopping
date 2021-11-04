<template>
<header>
<div  :key="task.id" v-if="task.reminder">


    <span :key="task.id" v-for="task in tasks">
    <Task @toggle-reminder="$emit('toggle-reminder', task.id)" @delete-task="$emit('delete-task', task.id)" :task="task" />
    </span>

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
  emits: ['delete-task', 'toggle-reminder'],
}
</script>
