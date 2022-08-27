<template>
    <div class="employee-list">
        <div class="m-table">
            <div class="m-header-table">
                <div class="m-title-table">Danh sách nhân viên</div>
                <button id="btn-add" class="btn btn-icon m-icon-add btn-add" @click = "btnOpenFormAddOnclick">Thêm nhân viên</button>
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
                            <th class="text-left">Mã nhân viên</th>
                            <th class="text-left">Họ và tên</th>
                            <th class="text-left">Giới tính</th>
                            <th class="text-center">Ngày sinh</th>
                            <th class="text-left">Điện thoại</th>
                            <th class="text-left">Email</th>
                            <th class="text-left">Chức vụ</th>
                            <th class="text-left">Phòng ban</th>
                            <th class="text-rigth">Mức lương cơ bản</th>
                            <th class="text-left">Tình trạng công việc</th>
                        </tr>
                    </thead>
                    <tbody>
                        <tr v-for="(employee) in employees" :key="employee.employeesID">
                            <td class="text-left">{{employee.employeesCode}}</td>
                            <td class="text-left">{{employee.employeesName}}</td>
                            <td class="text-left">{{employee.gender}}</td>
                            <td class="text-center">{{employee.dateOfBirth}}</td>
                            <td class="text-left">{{employee.phoneNumber}}</td>
                            <td class="text-left">{{employee.email}}</td>
                            <td class="text-left">{{employee.positionsID}}</td>
                            <td class="text-left">{{employee.departmentsID}}</td>
                            <td class="text-rigth">{{employee.salary}}</td>
                            <td class="text-left">{{employee.workStatus}}</td>
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
    <!-- @isShowDialog="showEmployeeDetail định nghĩa để dùng hàm emit -->
    
    <EmployeeDetail :isShow ="isShowDialog" @isShowDialog="showEmployeeDetail"/>
    
    
</template>

<script>
import axios from 'axios'
import EmployeeDetail from '@/view/employee/EmployeeDetail.vue'

    export default {
    name:"EmployeeList",
    components: {
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
        var me = this;
        console.log("created");
        // gọi api để lấy dữ liệu sử dụng axios
        axios
            .get("https://localhost:7285/api/v1/Employees?pageSize=8&pageNumber=1")
            .then((response) => {
            console.log(response.data.data);
            me.employees = response.data.data;
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
        console.log("beforeUpdate");
    
    },
    /**giai đoạn 6: updated
     * truy cập vào data, element
       truy cập vào trong dom
     */
    updated() {
        console.log("updated");

    },
    /**giai đoạn 7: beforeUnmount
     * truy cập vào data, element
       truy cập vào trong dom
     */
    beforeUnmount() {
        console.log("beforeUnmount");

    },
    unmounted() {
        console.log("unmounted");

    },

    

    methods: {

        /**
         * Author: NVHThai (26/08/2022)
         * Thêm mới nhân viên
         */
        btnOpenFormAddOnclick(){
            this.showEmployeeDetail(true);
        },


        /**
         * Author: NVHThai (26/08/2022)
         * @param {boolean} isShow: true là hiển thị, flase là ẩn form 
         */
        showEmployeeDetail(isShow){
            this.isShowDialog = isShow;
            console.log("a"+isShow);
        },
    },


    // formatDate() {
    // },
    
    
    data() {
        return {
            isShowDialog : false
        };
    },
    
}
</script>

<style scoped>
     @import url(../../css/details/table.css);
     @import url(../../css/details/bottom.css);
</style>