<template>
    <header>
    <div @dblclick="$emit('toggle-reminder', task.id)" :class="[task.reminder ? 'reminder': '', 'task']">
        <h3>{{task.programName}}
        <i @click="$emit('delete-task',task.id)" class="fas fa-times">X</i>
        </h3>
        
        <p>{{task.courseName}}</p>
        

        <p style="color:dodgerblue">{{task.courseLevel}}</p>
<!--<input type="submit" @click="$emit('enroll-task',task.id)" value="Enroll" class="btn btn-enroll">-->
 <Enrollment @btn-click="$emit('enroll-task',task.id)" :text="task.isEnrolled? 'Unenroll' : 'Enroll'" :color="task.isEnrolled? 'red' : 'green'"  />


    </div>
    </header>
</template>

<script>
import Enrollment from './Enrollment.vue'

export default{
    name: 'Task',
    props:{
        task: Object,
    },
    components:{
        Enrollment,
    }
 /*  methods:{
 onSubmit(e){
        e.preventDefault()

     this.$emit('enroll-task', this.task)
        
    },
   },*/
}
</script>

<style scope>

.fas{
    color: red;
margin-right: -1px;
}

.task{
    background: #f4f4f4;
    margin: 5px;
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
