<template>
    <header>
    <div @dblclick="$emit('toggle-reminder', task.id)" :class="[task.reminder ? 'reminder': '', 'task']">
        <h3>{{task.programName}}
       
        </h3>
        
        <p>{{task.courseName}}</p>
        
        <p style="color:dodgerblue">{{task.courseLevel}}</p>
    </div>
    </header>
</template>

<script>

export default{
    name: 'EnrollTask',
    props:{
        task: Object,
    },
   
}
</script>

<style scope>

.fas{
    color: red;
margin-right: -1px;
}
.fas-enroll{
    color: black;
    background-color: darkgreen;
    padding: 6px;
   margin-right: -1px;
   text-align: center;
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
