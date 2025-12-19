<template>
    <div class="topbar">
        <div class="top-left-side">
            <button>=</button>
        </div>
        TopBar
    </div>
</template>

<script>
export default {
    name: 'TopBarComponent'
}
</script>

<style scoped>
.topbar {
    height: 50px;
    width: 100%;
    display: flex;
    flex-direction: row;
    box-shadow: -1px 1px 23px -1px rgba(0,0,0,0.24);
    -webkit-box-shadow: -1px 1px 23px -1px rgba(0,0,0,0.24);
    -moz-box-shadow: -1px 1px 23px -1px rgba(0,0,0,0.24);
}
</style>