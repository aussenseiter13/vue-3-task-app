<script setup>
defineProps({
    task: Object,
});
</script>

<template>
    <li class="bg-gray-800 flex gap-4 justify-between px-4 py-2">
        <p>
            {{ task.name }}
        </p>
        <p
            v-text="task.completed ? 'Finished' : 'Not finished'"
            :class="task.completed ? 'text-teal-500' : 'text-red-500'"
        ></p>
    </li>
</template>
