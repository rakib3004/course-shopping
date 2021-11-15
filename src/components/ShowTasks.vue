<template>
<header>
  <div :key="task.id" v-for="task in enrolledTasks">
    <EnrollTask :task="task" />
    </div>
    </header>
</template>

<script>
import EnrollTask from './EnrollTask'


export default {
 name: 'ShowTasks',
   props:{
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



