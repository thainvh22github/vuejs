<template>
    <div class="m-table">
        <div class="m-header-table">
            <div class="m-title-table">Danh sách nhân viên</div>
            <button class="btn-icon m-icon-add btn-add">Thêm nhân viên</button>
        </div>
        <div class="m-toolbar-table">
            <div class="m-sort">
                <input class="input-icon m-icon-search m-sort-by-search" placeholder="Tìm kiếm theo Mã, Tên hoặc Số điện thoại">
                
                <div class="m-sort-by-department">
                    <input class="m-show-combobox" readonly="readonly" placeholder="Chọn thông tin">
                    <button class="m-icon-combobox">
                        <div class="m-icon-dropdown"></div>
                    </button>
                </div>

                <div class="m-sort-by-position">
                    <input class="m-show-combobox" readonly="readonly" placeholder="Chọn thông tin">
                    <button class="m-icon-combobox">
                        <div class="m-icon-dropdown"></div>
                    </button>
                </div>
            </div>
            <div class="toolbar">
                <button class="btn-toolbar m-icon-refresh toolbar-refresh"></button>
            </div>
        </div>
        <div class="m-data-table">
            <table>
                <thead>
                    <tr>
                        <td>mã nhân viên</td>
                        <td>tên nhân viên</td>
                        <td>giới tính</td>
                        <td>chức vụ</td>
                    </tr>
                </thead>
                <tbody>
                    <tr>
                        <td>NV0001</td>
                        <td>NV0001</td>
                        <td>NV0001</td>
                        <td>NV0001</td>
                    </tr>
                </tbody>
            </table>
        </div>
    </div>
</template>

<script>
    export default {
        
    }
</script>

<style scoped>
    @import url("../css/details/table.css")
</style>