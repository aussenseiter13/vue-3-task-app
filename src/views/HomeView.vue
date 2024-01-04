<script setup>
import MainContent from "@/components/MainContent.vue";
import TaskList from "@/components/Tasks/TaskList.vue";
</script>

<template>
    <MainContent>
        <div
            class="text-2xl bg-slate-800 w-full px-8 py-8 text-slate-300 font-bold flex flex-col gap-4"
        >
            <h1>HOME VIEW</h1>
        </div>
        <div class="px-8 py-8">
            <TaskList></TaskList>
        </div>
    </MainContent>
</template>
