<script setup>
defineProps({
    task: Object,
});
</script>

<template>
    <li>
        {{ task.name }}
    </li>
</template>
