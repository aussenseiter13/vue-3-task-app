<script setup>
import MainContent from "@/components/MainContent.vue";
import TaskList from "@/components/Tasks/TaskList.vue";
</script>

<template>
    <MainContent>
        <div class="text-2xl text-slate-300 font-bold flex flex-col gap-4">
            <h1>HOME VIEW</h1>
            <hr class="border-slate-500" />
        </div>
        <div>
            <TaskList></TaskList>
        </div>
    </MainContent>
</template>
