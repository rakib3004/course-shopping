<template>
<header>
    <div :key="task.id" v-for="task in tasks">
    <EnrollTask :task="task" />
    </div>
    </header>
</template>

<script>
import EnrollTask from './EnrollTask'


export default {
 name: 'ShowTasks',
   props:{
      enrolledTasks: Array,
  },
  components:{
      EnrollTask,
  },
 
}


</script>

<style scoped>
.doneList{
    background-color: darkgrey ;
    width: 100%;
    
}
</style>



