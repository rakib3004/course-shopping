<template>
<div class="container">
<Header  @toggle-add-task="toggleAddTask"  title="Online Course Program" :showAddTask="showAddTask" />

<div v-show="showAddTask">
<AddTask @add-task="addTask" />
</div>

<Tasks  @toggle-reminder="toggleReminder" @delete-task="deleteTask" @enroll-task="enrollTask"  :tasks="tasks"/>
<ShowTasks @toggle-reminder="toggleReminder" @delete-task="deleteTask" @enroll-task="enrollTask" :tasks="tasks" />

 </div>
</template>

<script>
import Header from './components/Header'
import Tasks from './components/Tasks'
import AddTask from './components/AddTask'
import ShowTasks from './components/ShowTasks'




export default {
  name: 'App',
  components: {
    Header, 
    Tasks,
    AddTask,
    ShowTasks,
  },

  methods:{

    addTask(task){

      this.tasks = [...this.tasks,task]

    },
    deleteTask(id){
      if(confirm('Are you sure?')){
this.tasks = this.tasks.filter((task)=>
 task.id !==id)
      }
   
    },
    enrollTask(id){
this.tasks = this.tasks.map((task) => task.id===id? {...task, isEnrolled: !task.isEnrolled}: task
 ) },
     toggleAddTask(){
      this.showAddTask=!this.showAddTask
    },

    toggleReminder(id){
this.tasks = this.tasks.map((task) => task.id===id? {...task, reminder: !task.reminder}: task
)
    },

  },
  data(){
    return{
      tasks: [],
      showAddTask: false,
    }
  },
  created(){
    this.tasks=[{
            id: 1,
            programName: 'Udemy',
            courseName: 'Latex Basics',
            courseLevel: 'Beginner',
            reminder:true,
            isEnrolled:true,
    },
    {
            id: 2,
            programName: 'Coursera',
            courseName: 'Operating System',
            courseLevel: 'Beginner',
            reminder:false,
            isEnrolled:true,

    },
    {
            id: 3,
            programName: '10 Minutes School',
            courseName: 'Communication Skills',
            courseLevel: 'Intermediate',
            reminder:true,
            isEnrolled:false,
    },
     {
            id: 4,
            programName: 'Bohubrihi',
            courseName: 'Digital Marketing',
            courseLevel: 'Beginner',
            reminder:true,
            isEnrolled:false,
    },
     {
            id: 5,
            programName: 'Coursera',
            courseName: 'Project Initialization',
            courseLevel: 'Advanced',
            reminder:true,
            isEnrolled:false,
    },
     {
            id: 6,
            programName: 'Udemy',
            courseName: 'DevOps Fundamentals',
            courseLevel: 'Beginner',
            reminder:true,
            isEnrolled:false,
    },
     {
            id: 7,
            programName: 'Udemy',
            courseName: 'Javascript Crash Course',
            courseLevel: 'Intermediate',
            reminder:true,
            isEnrolled:true,
    },
     {
            id: 8,
            programName: 'Interactive Cares',
            courseName: 'React Crash Course',
            courseLevel: 'Advanced',
            reminder:true,
            isEnrolled:false,
    },
     {
            id: 9,
            programName: '10 Minutes School',
            courseName: 'Project Management',
            courseLevel: 'Intermediate',
            reminder:false,
            isEnrolled:true,
    },
     {
            id: 10,
            programName: 'Coursera',
            courseName: 'Foundations of UX Design',
            courseLevel: 'Beginner',
            reminder:true,
            isEnrolled:false,
    },
     {
            id: 11,
            programName: 'Udemy',
            courseName: 'Corporate Finance',
            courseLevel: 'Intermediate',
            reminder:true,
            isEnrolled:false,
    },
     {
            id: 12,
            programName: 'Simplilearn',
            courseName: 'Ethical Hacking',
            courseLevel: 'Advanced',
            reminder:true,
            isEnrolled:false,
    },
    


    ]    
  }
}
</script>

<style>
@import url('https://fonts.googleapis.com/css2?family=Poppins:wght@300;400&display=swap');

*{
  box-sizing: border-box;
  margin: 0;
  padding: 0;
}

body{
  font-family: 'Poppins', sans-serif;

}
.container{
  max-width: 500px;
  margin: 30px auto;
  overflow: auto;
  min-height: 300px;
  border: 1px solid steelblue;
  padding: 30px;
  border-radius: 5px;
}
.btn{
  display: inline-block;
  background: black;
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

.btn:focus{
  outline: none;
}

.btn:active{

  transform: scale(0.98);
}

.btn-block{
  display: block;
  width: 100%;
}
.btn-enroll{
    width: 100%;
}
.enroll-section{
  
  text-align: center;
}
</style>
