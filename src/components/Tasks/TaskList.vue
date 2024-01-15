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

let displayCreateModal = ref(false);

function hideCreateModal() {
    displayCreateModal.value = false;
}

function createTask() {
    tasks.value.push({
        id: tasks.value.length + 1,
        name: newTask.value.name,
        completed: newTask.value.completed,
    });

    newTask.value.name = "";
    newTask.value.completed = false;
}

function deleteTask(task) {
    tasks.value = tasks.value.filter((item) => item.id != task.id);
}
</script>

<template>
    <div class="flex flex-col gap-8">
        <div>
            <button
                @click="displayCreateModal = true"
                class="bg-blue-600 hover:bg-blue-700 px-4 py-2 rounded-md font-bold"
            >
                Create
            </button>
            <CreateTaskModal
                :newTask="newTask"
                :display-create-modal="displayCreateModal"
                @createTask="createTask"
                @hideCreateModal="hideCreateModal"
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
