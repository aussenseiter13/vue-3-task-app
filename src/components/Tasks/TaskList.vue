<script setup>
import TaskItem from "@/components/Tasks/TaskItem.vue";

let tasks = [
    {
        id: 1,
        name: "Grab Launch",
        completed: true,
    },
];
</script>

<template>
    <ul>
        <TaskItem v-for="task in tasks" :key="task.id" :task="task"></TaskItem>
    </ul>
</template>
