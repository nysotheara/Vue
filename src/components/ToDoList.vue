<script setup>
// Option API
// export default {
//     data(){
//         return{
//             name: "John Doe",
//             status: 'pending',
//             tasks: ["Vue", "React", "Angular"],
//             link: "https://www.google.com"
//         }
//     },
//     methods: {
//         toggleStatus() {
//             if (this.status === 'active') this.status = 'pending'
//             else if (this.status === 'pending') this.status = 'inactive'
//             else this.status = 'active'
//         }
//     }
// }

// Composition API
import { ref } from 'vue';
const name = ref("Sotheara");
const status = ref('active');
const tasks = ref(['Vue', "React", "Angular"]);
const newTask = ref('');

const toggleStatus = () => {
    if (status.value === 'active') status.value = 'pending'
    else if (status.value === 'pending') status.value = 'inactive'
    else status.value = 'active';
};

const addTask = () => {
    if(newTask.value.trim() !== ''){
        tasks.value.push(newTask.value);
        newTask.value = '';
    }
}

const deleteTask = (index) => {
    tasks.value.splice(index, 1);
}

</script>

<template>
    <h1>{{ name }}</h1>
    <p v-if="status === 'active'">User is Active</p>
    <p v-else-if="status === 'pending'">User is pending</p>
    <p v-else> User is inactive</p>

    <form @submit.prevent="addTask">
        <label for="newTask">Add Task</label>
        <input type="text" id="newTask" v-model="newTask">
        <button type="submit">Submit</button>
    </form>

    <h3>Task:</h3>
    <ul>
        <li v-for="(task, index) in tasks" :key="task">
            <span>
                Task : {{ task }}
            </span> 
            <button @click="deleteTask(index)">X</button>
        </li>
    </ul>
    <a :href="link">Click for Google</a><br>
    <button v-on:click="toggleStatus">Change Status</button>
</template>