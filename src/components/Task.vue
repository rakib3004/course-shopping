<template>
    <header>
    <div @dblclick="$emit('toggle-reminder', task.id)" :class="[task.reminder ? 'reminder': '', 'task']">
        <h3>{{task.text}}
        <i @click="$emit('delete-task',task.id)" class="fas fa-times">X</i>
        </h3>
        
        <p>{{task.day}}</p>

    </div>
    </header>
</template>

<script>

export default{
    name: 'Task',
    props:{
        task: Object,
    },
   
}
</script>

<style scope>

.fas{
    color: red;
}
.task{
    background: #f4f4f4;
    margin: 5px;
    border-left: 5px solid red;
    padding: 10px 20px;
    cursor: pointer;
}

.task.reminder{
    border-left: 5px solid green;

}


.task h3{
    display: flex;
    align-items: center;
    justify-content: space-between;
}

</style>
