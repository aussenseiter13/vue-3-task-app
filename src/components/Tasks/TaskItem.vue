<script setup>
defineProps({
    task: Object,
});
</script>

<template>
    <li class="bg-gray-800 flex gap-4 justify-between px-4 py-2">
        <div>
            <p>
                {{ task.name }}
            </p>
            <p>{{ task.id }}</p>
            <p
                v-text="task.completed ? 'Finished' : 'Not finished'"
                :class="task.completed ? 'text-teal-500' : 'text-red-500'"
            ></p>
        </div>
        <div>
            <button
                class="bg-red-500 px-2 rounded-md font-bold"
                @click="$emit('deleteTask', task)"
            >
                Delete
            </button>
        </div>
    </li>
</template>
