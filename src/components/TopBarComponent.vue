<template>
    <div class="topbar">
        <div class="top-left-side">
            <button @click="toggleSidebar">=</button>
            TopBar
        </div>
        <div class="top-right-side">
            <div class="avatar"></div>
            Chango
        </div>
    </div>
</template>

<script>
export default {
    name: 'TopBarComponent',
    emits: ['toggle-sidebar'],
    methods: {
        toggleSidebar() {
            this.$emit('toggle-sidebar');
        },
        logout() {
            console.log('Logout clicked');
        }
    }
}
</script>

<style scoped>
.topbar {
    height: 50px;
    width: 100%;
    display: flex;
    flex-direction: row;
    justify-content: space-between;
    box-shadow: -1px 1px 5px -1px rgba(0,0,0,0.24);
    -webkit-box-shadow: -1px 1px 5px -1px rgba(0,0,0,0.24);
    -moz-box-shadow: -1px 1px 5px -1px rgba(0,0,0,0.24);
    position: relative;
    z-index: 1;
}
</style>