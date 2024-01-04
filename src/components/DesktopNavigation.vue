<script setup>
import { RouterLink } from "vue-router";
</script>

<template>
    <header
        class="bg-slate-950 fixed h-full top-0 left-0 min-w-64 px-8 py-8 flex flex-col gap-8"
    >
        <div class="flex flex-col gap-8 text-center">
            <h3 class="font-bold text-gray-300">TASK APP</h3>
            <hr class="border-slate-800" />
        </div>
        <nav class="flex flex-col items-start gap-4">
            <RouterLink
                to="/"
                class="bg-slate-900 text-slate-400 font-bold w-full text-center py-2 rounded-md hover:bg-slate-800 hover:text-slate-300"
                >Home</RouterLink
            >
            <RouterLink
                to="/about"
                class="bg-slate-900 text-slate-400 font-bold w-full text-center py-2 rounded-md hover:bg-slate-800 hover:text-slate-300"
                >About</RouterLink
            >
        </nav>
    </header>
</template>
