<template>
    <div class="m-bottom">
        <div class="m-showtotal-emloyee">
            Hiển thị 1-10/1000 nhân viên
        </div>
        <div class="m-paging">
            <button class="btn-first-page m-icon-first-page"></button>
            <button class="btn-prev-page m-icon-prev-page"></button>
            <button class="btn-page-1 m-page-active">1</button>
            <button class="btn-page-2">2</button>
            <button class="btn-page-3">3</button>
            <button class="btn-page-4">4</button>
            <button class="btn-next-page m-icon-next-page"></button>
            <button class="btn-last-page m-icon-last-page"></button>
        </div>
        <div class="m-employee-paging">10 nhân viên trên trang</div>
    </div>
</template>

<script>
    export default {
        
    }
</script>

<style scoped>
    @import url("../css/details/bottom.css")
</style>