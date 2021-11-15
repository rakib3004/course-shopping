<template>
    <form @submit="onSubmit" class="add-form">
    <div class="form-control">
    <label >Program Name</label>
<input type="text" v-model="programName" name="programName" placeholder="Add Program Name"/>
    </div>

<div class="form-control">
<label >Course Name</label>
<input type="text" v-model="courseName" name="courseName" placeholder="Add Course Name"/>
</div>

<div class="reminder-control">
<label >Set Reminder</label>
<input type="checkbox" v-model="reminder" name="reminder"/>
</div>
<div class="form-control">
<label style="font-size:17px" >Choose Level</label>
</div>

<div class="radio-control">
<input type="radio" name="Beginner" value="Beginner" v-model="level">
<label for="beginner">Beginner</label>

<input type="radio" name="Intermediate" value="Intermediate" v-model="level">
<label for="intermediate">Intermediate</label>

<input type="radio" name="Advanced" value="Advanced" v-model="level">
<label for="advanced">Advanced</label>

</div>


<input type="submit" value="Save Task" class="btn btn-block">
    </form>

</template>

<script>

export default{

name: 'AddTask',
data(){
    return{
        programName: '',
        courseName: '',
        courseLevel:'',
        isEnrolled:false,
        reminder: false,
    }
},
methods:{
    onSubmit(e){
        e.preventDefault()

        if(!this.programName){
            alert('Please add a task')
            return
        }
        const newTask={
           
            id: Math.floor(Math.random()*100000),
            programName: this.programName,
            courseName: this.courseName,
            courseLevel: this.level,
            reminder:this.reminder,
            isEnrolled:this.isEnrolled,
        }
        console.log('Add a tasks');
        this.$emit('add-task', newTask)

        this.programName=''
        this.courseName=''
        this.courseLevel=''
        this.reminder=false
        this.isEnrolled=false

    },
}

}
</script>

<style scoped>
.add-form{
    margin-bottom: 40px;
}

.form-control{
    margin: 20px 0;
}

.form-control label{
    display: block;
}

.form-control input{

    width: 100%;
    height: 40px;
    margin: 5px;
    padding: 3px 7px;
    font-size: 17px;
}
.form-control-check{
    display: flex;
    align-items: center;
    justify-content: space-between;
}

.form-control-check label{
   flex: 1;
}

.form-control-check input{
    flex: 2;
    height: 20px;

}
.radio-control{

     width: 100%;
    height: 40px;
    margin: 5px;
    padding: 3px 7px;
    font-size: 17px;
}
.radio-control label{

margin-right: 10px ;

}

.reminder-control{
    margin: 20px 0;
    font-size: 17px;
    
}

.reminder-control label{
  margin-right: 10px;
}

.reminder-control input{

    width: 10%;
    height: 25px;
    margin: 5px;
    padding: 3px 7px;
    font-size: 25px;
}
</style>