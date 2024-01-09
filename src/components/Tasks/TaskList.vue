<script setup>
import { ref } from "vue";
import TaskItem from "@/components/Tasks/TaskItem.vue";
import CreateTaskModal from "@/components/Tasks/CreateTaskModal.vue";

let tasks = ref([
    {
        id: 1,
        name: "Grab Launch",
        completed: true,
    },
    {
        id: 2,
        name: "Practice C++",
        completed: false,
    },
]);

let newTask = ref({
    name: "test",
    completed: true,
});

function createTask() {
    console.log("HIT FUNCION");

    console.log(newTask.value.name);

    // tasks.value.push({
    //     id: tasks.value.length + 1,
    //     name: newTask.name.value,
    //     completed: newTask.completed,
    // });

    // newTask.name.value = "";
    // newTask.completed = false;
}

function deleteTask(task) {
    tasks.value = tasks.value.filter((item) => item.id != task.id);
}
</script>

<template>
    <div class="flex flex-col gap-8">
        <div>
            <button
                class="bg-blue-600 hover:bg-blue-700 px-4 py-2 rounded-md font-bold"
            >
                Create
            </button>
            <CreateTaskModal
                :newTask="newTask"
                @createTask="createTask"
            ></CreateTaskModal>
        </div>
        <ul class="flex flex-col gap-4">
            <TaskItem
                @deleteTask="deleteTask"
                v-for="task in tasks"
                :key="task.id"
                :task="task"
            ></TaskItem>
        </ul>
    </div>
</template>
