<template>
    <div class="topbar">
        <div class="top-left-side">
            <button @click="toggleSidebar" class="push-side-nav-button">
                <img :src="ICONS.MENU" alt="">
            </button>
            <span>TopBar</span>
        </div>
        <div class="top-right-side">
            <button>
                <img :src="ICONS.AVATAR" alt="">
            </button>
            Chango
        </div>
    </div>
</template>

<script>
import ICONS from '@/constants/icons';

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
    },
    data() {
        return {
            ICONS
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
.topbar .push-side-nav-button {
    aspect-ratio: 1 / 1;
    height: 100%;
    border: none;
    background-color: transparent;
    border-radius: 100%;
    padding: 0 !important;
}
.topbar .push-side-nav-button:hover {
    background-color: rgba(0, 0, 0, 0.05);
}
.topbar .push-side-nav-button img {
    height: 100%;
}

.topbar .top-left-side {
    display: flex;
    flex-direction: row;
    align-items: center;
    gap: 10px;
    font-weight: bold;
}
</style>