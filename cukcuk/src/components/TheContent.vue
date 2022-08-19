<template>
    <div class="m-content">
        <TheHeader/>
        <TheTable/>
        <TheBottom/>
    </div>
</template>

<script>
    import TheHeader from './TheHeader.vue'
    import TheTable from './TheTable.vue'
    import TheBottom from './TheBottom.vue';

    export default {
    components: { TheHeader, TheTable, TheBottom }
}
</script>

<style scoped>
    @import url(../css/details/content.css);
</style>