<template>
  <div class="app-container">
    <SideBarComponent 
    :toggled="toggled"
    @changeViewSignal="(module: Module) => console.log('View changed to:', module.nombre)"
     />
    <ComponentContainerComponent @toggle-sidebar="handleToggleSidebar" />
  </div>
</template>

<script setup lang="ts">
import { ref } from 'vue';
import ComponentContainerComponent from './components/ComponentContainerComponent.vue';
import SideBarComponent from './components/SideBarComponent.vue';
import type { Module } from './models/module';

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