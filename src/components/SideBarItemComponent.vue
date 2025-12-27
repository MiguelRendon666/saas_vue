<template>
<div class="side-bar-item" @click="setNewView">
    <div class="icon">
        <img :src="module.icon" alt="">
    </div>
    <span>{{module.nombre}}</span>
</div>
</template>

<script lang="ts">
import { Module } from '@/models/module';

export default {
    name: 'SideBarItemComponent',
    signals: ['changeViewSignal'],
    props: {
        active: {
            type: Boolean,
            default: true
        },
        module : {
            type: Object as () => Module,
            required: true
        }
    },
    methods: {
        setNewView() {
            this.$emit('changeViewSignal', this.module);
        }
    },
}
</script>

<style scoped>
.side-bar-item {
    display: flex;
    flex-direction: row;
    align-items: center;
    transition: 0.4s ease;
}
.side-bar-item:hover {
    background-color: #f0f0f0;
    cursor: pointer;
}

.side-bar-item .icon{
    width: var(--sidebar-min-width);
    height: var(--sidebar-min-width);
}
.side-bar-item .icon img{
    width: var(--sidebar-min-width);
    height: var(--sidebar-min-width);
}
</style>