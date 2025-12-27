<template>
  <div class="app-container">
    <SideBarComponent 
    :toggled="toggled"
    @changeViewSignal="handleChangeView"
     />
    <ComponentContainerComponent 
    ref="ComponentContainer"
    @toggle-sidebar="handleToggleSidebar" />
  </div>
</template>

<script setup lang="ts">
import { ref } from 'vue';
import ComponentContainerComponent from './components/ComponentContainerComponent.vue';
import SideBarComponent from './components/SideBarComponent.vue';
import type { Module } from './models/module';

const toggled = ref(true);

const componentContainer = ref<InstanceType<typeof ComponentContainerComponent> | null>(null);

const handleToggleSidebar = () => {
  toggled.value = !toggled.value;
};

const handleChangeView = (module: Module) => {
  console.log(componentContainer);
  componentContainer.value?.ChangeView(module);
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