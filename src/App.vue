<template>
  <div class="app-container">
    <SideBarComponent :toggled="toggled" />
    <ComponentContainerComponent @toggle-sidebar="handleToggleSidebar" />
  </div>
</template>

<script setup>
import { ref } from 'vue';
import ComponentContainerComponent from './components/ComponentContainerComponent.vue';
import SideBarComponent from './components/SideBarComponent.vue';

const toggled = ref(true);

const handleToggleSidebar = () => {
  toggled.value = !toggled.value;
};
</script>

<style scoped>
  .app-container {
    display: flex;
    flex-direction: row;
    max-height: 100vh;
    height: 100vh;
  }
</style>