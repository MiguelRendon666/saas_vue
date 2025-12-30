<template>
    <div :class="['sidebar', { toggled }]">
        <div class="header">
            Header
        </div>

        <div class="body">
        <SideBarItemComponent 
        v-for="module in MODULES" 
        :active="false" 
        :module="module"
        @changeViewSignal="handleChangeView"
        />
        </div>

        <div class="footer">
            footer
        </div>
    </div>
</template>

<script lang="ts">
import { Module } from '@/models/module';
import SideBarItemComponent from './SideBarItemComponent.vue';
import { MODULES } from '@/constants/modules';

export default {
    name: 'SideBarComponent',
    components: {
        SideBarItemComponent
    },
    signals: ['changeViewSignal'],
    props: {
        toggled: {
            type: Boolean,
            default: true
        }
    },
    methods: {
        handleChangeView(module: Module) {
            this.$emit('changeViewSignal', module);
        }
    },
    data() {
        return {
            MODULES
        }
    }
}
</script>

<style>
.sidebar {
    display: flex;
    flex-direction: column;
    max-width: 60px;
    width: 100%;
    height: 100%;
    max-height: 100vh;
    transition: 0.5s ease;
    position: relative;
    z-index: 100;
    background-color: white;
    overflow: hidden;
}
.sidebar.toggled {
    max-width: 250px;
}

.sidebar .header {
    height: 50px;
    opacity: 0;
    max-height: 90px;
    padding: 0;
    overflow: hidden;
    border-bottom: 1px solid lightgray;
    transition: 0.5s ease;
}
.sidebar.toggled .header {
    height: 100%;
    opacity: 1;
    padding: 1rem;
} 

.sidebar .body {
    flex-grow: 1;
    max-height: calc(100vh - 160px);
    overflow-y: auto;
    overflow-x: hidden;
}

.sidebar .footer {
    height: 0%;
    opacity: 0;
    max-height: 70px;
    padding: 1rem;
    overflow: hidden;
    transition: 0.5s ease;
    border-top: 1px solid lightgray;
}
.sidebar.toggled .footer {
    height: 100%;
    opacity: 1;
}
</style>