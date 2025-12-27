<template>
<div class="side-bar-item">
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
    props: {
        active: {
            type: Boolean,
            default: true
        },
        module : {
            type: Object as () => Module,
            required: true
        }
    }
}
</script>

<style scoped>
.side-bar-item {
    display: flex;
    flex-direction: row;
    align-items: center;
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