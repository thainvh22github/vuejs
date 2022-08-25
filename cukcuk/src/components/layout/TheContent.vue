<template>
    <div class="m-content">
        <TheHeader/>
        <router-view></router-view>
    </div>
</template>

<script>
    import TheHeader from './TheHeader.vue';

    export default {
    components: {TheHeader}
}
</script>

<style scoped>
    @import url(../../css/details/content.css);
</style>