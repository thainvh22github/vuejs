<template>
    <div class="employee-list">
        <div class="m-table">
            <div class="m-header-table">
                <div class="m-title-table">Danh sách nhân viên</div>
                <button id="btn-add" class="btn btn-icon m-icon-add btn-add">Thêm nhân viên</button>
            </div>
            <div class="m-toolbar-table">
                <div class="m-sort">
                    <input class="input input-icon m-icon-search m-sort-by-search" placeholder="Tìm kiếm theo Mã, Tên hoặc Số điện thoại">
                    
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
                            <td class="text-left">Mã nhân viên</td>
                            <td class="text-left">Họ và tên</td>
                            <td class="text-left">Giới tính</td>
                            <td class="text-center">Ngày sinh</td>
                            <td class="text-left">Điện thoại</td>
                            <td class="text-left">Email</td>
                            <td class="text-left">Chức vụ</td>
                            <td class="text-left">Phòng ban</td>
                            <td class="text-rigth">Mức lương cơ bản</td>
                            <td class="text-left">Tình trạng công việc</td>
                        </tr>
                    </thead>
                    <tbody>
                        <tr v-for="employee in employees" :key="employee.departmentsID">
                            <td class="text-left">{{employee.departmentsCode}}</td>
                            <td class="text-left">{{employee.departmentsName}}</td>
                            <td class="text-left">Nam</td>
                            <td class="text-center">22/10/20000</td>
                            <td class="text-left">0868886703</td>
                            <td class="text-left">thainvh22@gmail.com</td>
                            <td class="text-left">Fresher</td>
                            <td class="text-left">Viện</td>
                            <td class="text-rigth">3.000.000</td>
                            <td class="text-left">Đang đi làm</td>
                        </tr>
                    </tbody>
                </table>
            </div>
        </div>
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
    </div>

    <EmployeeDetail />
</template>

<script>
import axios from 'axios'
import EmployeeDetail from './EmployeeDetail.vue'
    export default {
    name: "EmployeeList",
    component: {
        EmployeeDetail
    },
    /**giai đoạn 1: beforeCreate ( setup() )
     * không thể truy cập vào data, Dom
     */
    beforeCreate() {
        console.log("beforeCreate");
    },
    /**giai đoạn 2: created
     * truy cập vào data, event, methos
        chưa thể truy cập vào trong dom

        dùng để load dữ liệu cho sớm
     */
    created() {
        let me = this;
        console.log("created");
        // gọi api để lấy dữ liệu sử dụng axios
        axios
            .get("https://localhost:7285/api/Departments")
            .then((response) => {
            console.log(response.data);
            me.employees = response.data;
        });
    },
    /**giai đoạn 3: beforeMount
     * truy cập vào data, element
        chưa thể truy cập vào trong dom
     */
    beforeMount() {
        console.log("beforeMount");
    },
    /**giai đoạn 4: mounted
     * truy cập vào data, element
       truy cập vào trong dom

     */
    mounted() {
        console.log("mounted");
    },
    /**giai đoạn 5: beforeUpdate
     * truy cập vào data, element
       truy cập vào trong dom

       nên làm validate dữ liệu hàm event.data lấy ra tưng dữ liệu
       lấy hết data thì event.curentTarget.value
     */
    beforeUpdate() {
    },
    /**giai đoạn 6: updated
     * truy cập vào data, element
       truy cập vào trong dom
     */
    updated() {
    },
    /**giai đoạn 7: beforeUnmount
     * truy cập vào data, element
       truy cập vào trong dom
     */
    beforeUnmount() {
    },
    unmounted() {
    },
    methods: {
        btnAddOnClick() {
            return "add on click";
        },
        getName() {
            return this.fullName;
        }
    },
    formatDate() {
    },
    data() {
        return {
            fullName: "Nguyen Vu Hai Thai",
            employees: null
        };
    },
    components: { EmployeeDetail }
}
</script>

<style scoped>
     @import url(../../css/details/table.css);
     @import url(../../css/details/bottom.css);
</style>