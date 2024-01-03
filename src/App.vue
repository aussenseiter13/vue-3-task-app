<script setup>
import { RouterLink, RouterView } from "vue-router";
import MainContainer from "./components/MainContainer.vue";
import DesktopNavigation from "./components/DesktopNavigation.vue";
</script>

<template>
    <MainContainer>
        <DesktopNavigation></DesktopNavigation>
        <RouterView />
    </MainContainer>
</template>
