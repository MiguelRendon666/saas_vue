<template>
    <div class="ViewContainer">
        <TopBarComponent />
        <div class="ComponentContainer">
            <div v-for="i in 200" :key="i">body {{ i }}</div>
        </div>
    </div>
</template>

<script>
import TopBarComponent from './TopBarComponent.vue';

export default {
    name: 'ComponentContainerComponent',
    components: {
        TopBarComponent
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