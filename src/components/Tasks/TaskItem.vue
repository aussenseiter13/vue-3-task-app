<script setup>
defineProps({
    task: Object,
});
</script>

<template>
    <li class="bg-gray-800 flex flex-row gap-8 justify-between px-4 py-2">
        <div class="flex flex-row gap-4">
            <p>
                {{ task.name }}
            </p>
            <p>{{ task.id }}</p>
            <p
                v-text="task.completed ? 'Finished' : 'Not finished'"
                :class="task.completed ? 'text-teal-500' : 'text-red-500'"
            ></p>
        </div>
        <div class="flex gap-4 items-center">
            <button
                class="bg-blue-600 hover:bg-blue-700 px-2 rounded-md font-bold"
            >
                Edit
            </button>
            <button
                class="bg-red-600 hover:bg-red-700 px-2 rounded-md font-bold"
                @click="$emit('deleteTask', task)"
            >
                Delete
            </button>
        </div>
    </li>
</template>
