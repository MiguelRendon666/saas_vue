<template>
    <div class="ViewContainer">
        <TopBarComponent @toggle-sidebar="$emit('toggle-sidebar')" />
        <div class="ComponentContainer">
            <div v-for="i in 200" :key="i">body {{ i }}</div>
        </div>
    </div>
</template>

<script lang="ts">
import TopBarComponent from './TopBarComponent.vue';
import { Module } from '@/models/module';

export default {
    name: 'ComponentContainerComponent',
    components: {
        TopBarComponent
    },
    emits: ['toggle-sidebar'],
    methods: {
        ChangeView(module : Module) {
            console.log('View changed to:', module.nombre);
        },
    },
}
</script>

<style scoped>
.ViewContainer {
    display: flex;
    flex-direction: column;
    width: 100%;
    height: 100%;
    max-height: 100vh;
    position: relative;
    z-index: 1;
}
.ComponentContainer {
    width: 100%;
    height: 100%;
    max-height: calc(100vh - 50px);
    overflow: auto;
    padding-top: 1rem;
    padding-inline: 1rem;
    padding-bottom: 2rem;
    box-sizing: border-box;
}
</style>