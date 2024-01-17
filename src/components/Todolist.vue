<script setup>
import { ref } from "vue"

const tasks = ref([
    {id: 1, name:  'Task Name 1' , time: '30'},
    // {id: 2, name:  'Task Name 2',  time: '40'},
   

] );

function addNewTask(){
    const newTask = {
        id: tasks.value.length+1,
         name: `Task Name ${tasks.value.length+1}`,
            time: `Time ${tasks.value.length+30
        }`
    };
    tasks.value.push(newTask);
}
function delateNewTask(){
    const newTask = {
        id: tasks.value.length+1,
        name: `Task ${tasks.value.length+1}`
    };
    tasks.value.pop(newTask);
}
function submit(){
   alert("submit task")
}



</script>
  <template>

    <!-- <button  v-for = "task in tasks"  :key = " task.id ">{{ task.name }}  {{ task.time }}</button> -->
<div class="container">
    <p v-for = "task in tasks"  :key = " task.id " >
    <li>{{ task.name }}  {{ task.time }} </li></p>
    <button @click="delateNewTask ()"  class="btn-delete"> Delete new task</button>
<br>        

</div>

<button @click=" addNewTask ()"> Add new task</button>

<br>
<input type="text"  placeholder="task name" /> <br>
<input type="text"  placeholder="task name" /> <br>

<button @click=" submit ()"> submit</button>


  </template>



  <style scoped>
.container{
    display: flex;
}
.btn-delete{
    background-color: aqua;

}
input[type=text], select, textarea {
  width: 100%;
  padding: 12px;
  border: 1px solid #ccc;
  border-radius: 4px;
  resize: vertical;
}


</style>