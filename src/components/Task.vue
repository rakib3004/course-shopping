<template>
    <header>
    <div @dblclick="$emit('toggle-reminder', task.id)" :class="[task.reminder ? 'reminder': '', 'task']">
        <h3>{{task.programName}}
        <i @click="$emit('delete-task',task.id)" class="fas fa-times">X</i>
        </h3>
        
        <p>{{task.courseName}}</p>
        

        <p style="color:dodgerblue">{{task.courseLevel}}</p>
<input type="submit" @click="$emit('enroll-task',task.id)" value="Enroll" class="btn btn-enroll">

    </div>
    </header>
</template>

<script>

export default{
    name: 'Task',
    props:{
        task: Object,
    },
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
.btn-enroll{
    color: black;
    background: darkgreen;
    padding: 6px;
   margin-right: -1px;
   text-align: center;
     display: block;
  width: 100%;
  display: inline-block;
  color: #fff;
  border: none;
  padding: 10px 20px;
  margin: 5px;
  border-radius: 5px;
  cursor: pointer;
  text-decoration: none;
  font-size: 15px;
  font-family: inherit;
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
