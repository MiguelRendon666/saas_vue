<template>
    <div class="sidebar toggled">
        <div class="header">
            Header
        </div>

        <div class="body">
        <div v-for="i in 10" :key="i">body {{ i }}</div>
        </div>

        <div class="footer">
            footer
        </div>
    </div>
</template>

<script>
export default {
    name: 'SideBarComponent'
}
</script>

<style scoped>
.sidebar {
    display: flex;
    flex-direction: column;
    max-width: 60px;
    width: 100%;
    height: 100%;
    max-height: 100vh;
    transition: 0.5s ease;
}
.sidebar.toggled {
    max-width: 250px;
}

.sidebar .header {
    height: 100%;
    max-height: 90px;
    padding: 1rem;
}

.sidebar .body {
    flex-grow: 1;
    max-height: calc(100vh - 160px);
    overflow-y: auto;
}

.sidebar .footer {
    height: 100%;
    max-height: 70px;
    padding: 1rem;
}
</style>