<template>
    <div class="m-header">
        <div class="m-combobox m-combobox-restaurants">
            <input class="m-show-combobox" readonly="readonly" placeholder="Chọn thông tin">
            <button class="m-icon-combobox">
                <div class="m-icon-dropdown"></div>
            </button>
        </div>
        <div class="m-info-user">
            <div class="m-avatar">
                <div class="m-icon-avatar-default"></div>
            </div>
            <div class="m-user-name">Nguyễn Vũ Hải Thái</div>
            <div class="m-option-avatar">
                <div class="m-icon-option"></div>
            </div>
        </div>
    </div>
</template>

<script>
    export default {
        
    }
</script>

<style scoped>
        @import url(../../css/details/header.css);
</style>