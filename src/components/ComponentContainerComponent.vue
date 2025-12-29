<template>
    <div class="ViewContainer">
        <TopBarComponent 
        :title="title" 
        @toggle-sidebar="$emit('toggle-sidebar')" />
        <div class="ComponentContainer">
            <component v-if="currentComponent" :is="currentComponent" />
        </div>
        <!-- <LoadingScreenComponent /> -->
    </div>
</template>

<script lang="ts">
import LoadingScreenComponent from './LoadingScreenComponent.vue';
import TopBarComponent from './TopBarComponent.vue';
import { Module } from '@/models/module';

export default {
    name: 'ComponentContainerComponent',
    components: {
        TopBarComponent, LoadingScreenComponent
    },
    emits: ['toggle-sidebar'],
    methods: {
        ChangeView(module : Module) {
            this.title = module.nombre;
            this.currentComponent = module.type;
        },
    },
    data() {
        return {
            title: '',
            currentComponent: null as any,
        };
    }
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
    position: relative;
    background-color: #f5f5f5;
}
</style>