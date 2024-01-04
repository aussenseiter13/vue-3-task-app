<script setup>
import TaskItem from "@/components/Tasks/TaskItem.vue";
import { ref, onBeforeMount, reactive } from "vue";

let tasks = reactive([
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

let newTask = {
    name: ref(""),
    completed: ref(false),
};

function addTask() {
    tasks.push({
        id: tasks.length + 1,
        name: newTask.name.value,
        completed: newTask.completed,
    });

    newTask.name.value = "";
    newTask.completed = false;
}
</script>

<template>
    <div class="flex flex-col gap-8">
        <form
            @submit.prevent="addTask"
            class="bg-slate-800 flex flex-col gap-6 px-4 py-4 border border-slate-700 rounded-md text-slate-300"
        >
            <div class="flex flex-col gap-2">
                <label for="" class="">Task name</label>
                <input
                    v-model="newTask.name.value"
                    type="text"
                    class="bg-slate-700"
                    placeholder="Example name"
                />
            </div>
            <div class="flex flex-row-reverse justify-end gap-2 items-center">
                <label for="">Completed</label>
                <input
                    type="checkbox"
                    v-model="newTask.completed"
                    :checked="newTask.completed"
                />
            </div>
            <button
                :disabled="newTask.name.value.length ? 0 : !0"
                class="bg-slate-600 py-2 rounded-md font-bold text-md hover:bg-teal-600 disabled:bg-slate-700 disabled:text-slate-500 disabled:cursor-not-allowed"
            >
                Create task
            </button>
        </form>
        <ul class="flex flex-col gap-4">
            <TaskItem
                v-for="task in tasks"
                :key="task.id"
                :task="task"
            ></TaskItem>
        </ul>
    </div>
</template>
