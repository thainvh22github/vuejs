<template>
    <div id="employeeDetail" class="m-dialog" v-bind:class="{isShowDialog: isShow}" >
        <div id="formadd" class="m-dialog-modal">
            <div class="m-header-form-add">
                <div class="m-title-form-add">THÔNG TIN NHÂN VIÊN</div>
                <div class="m-icon-x btn-close-form-add" id="btn-close" @click = "btnCloseFormAddOnclick"></div>
            </div>

            <div class="m-main-form-add">
                <div class="m-avatar-form-add">
                    <div class="m-icon-default-avatar m-default-avatar"></div>
                    <div class="m-text-avatar">(Vui lòng chọn ảnh có định dạng .jpg, .jpeg, .png, .gif)</div>
                </div>
                <div class="m-content-form-add">

                    <div class="m-text-header-form">A. THÔNG TIN CHUNG</div>
                    <div class="m-line-form mt-4 mf-15"></div>
                    <div class="m-employeecode-employeename m-display-98 mt-10">
                        <div class="m-container">
                            <div class="m-text-form">Mã nhân viên</div>
                            <input type="text" class="input width-100 m-employeecode">
                        </div>
                        <div class="m-container">
                            <div class="m-text-form">Họ và tên</div>
                            <input type="text" class="input width-100 m-employeename">
                        </div>
                        
                    </div>
                    <div class="m-dateofbirth-gender m-display-98 mt-10">
                        <div class="m-container">
                            <div class="m-text-form">Ngày sinh</div>
                            <input type="date" class="input width-100 m-dateofbirth">
                        </div>
                        <div class="m-container">
                            <div class="m-text-form">Giới tính</div>
                            <div class="m-combobox m-combobox-gender">
                                <input class="m-show-combobox" readonly="readonly" placeholder="Chọn thông tin">
                                <button class="m-icon-combobox">
                                    <div class="m-icon-dropdown"></div>
                                </button>
                            </div>
                        </div>
                    </div>
                    <div class="m-identitynumber-identityissueddate m-display-98 mt-10">
                        <div class="m-container">
                            <div class="m-text-form">Số CMTND/ Căn cước</div>
                            <input type="text" class="input width-100 m-identitynumber">
                        </div>
                        <div class="m-container">
                            <div class="m-text-form">Ngày cấp</div>
                            <input type="date" class="input width-100 m-identityissueddate">
                        </div>
                        
                    </div>

                    <div class="m-parent-identityissuedplace m-display-98 mt-10">
                        <div class="m-container">
                            <div class="m-text-form">Nơi cấp</div>
                            <input type="text" class="input m-identityissuedplace">
                        </div>
                    </div>

                    <div class="m-email-numberphone m-display-98 mt-10">
                        <div class="m-container">
                            <div class="m-text-form">Email</div>
                            <input type="text" class="input width-100 m-email">
                        </div>
                        <div class="m-container">
                            <div class="m-text-form">Số điện thoại</div>
                            <input type="text" class="input width-100 m-numberphone">
                        </div>
                        
                    </div>

                    <div class="m-text-header-form mt-10">B. THÔNG TIN CÔNG VIỆC</div>
                    <div class="m-line-form mt-4 mf-15"></div>

                    <div class="m-position-department m-display-98 mt-10">
                        <div class="m-container">
                            <div class="m-text-form">Vị trí</div>
                            <div class="m-combobox m-combobox-position">
                                <input class="m-show-combobox" readonly="readonly" placeholder="Chọn thông tin">
                                <button class="m-icon-combobox">
                                    <div class="m-icon-dropdown"></div>
                                </button>
                            </div>
                        </div>
                        <div class="m-container">
                            <div class="m-text-form">Phòng ban</div>
                            <div class="m-combobox m-combobox-department">
                                <input class="m-show-combobox" readonly="readonly" placeholder="Chọn thông tin">
                                <button class="m-icon-combobox">
                                    <div class="m-icon-dropdown"></div>
                                </button>
                            </div>
                        </div>
                    </div>

                    <div class="m-taxcode-salary m-display-98 mt-10">
                        <div class="m-container">
                            <div class="m-text-form">Mã số thuế cá nhân</div>
                            <input type="text" class="input width-100 m-taxcode">

                        </div>
                        <div class="m-container">
                            <div class="m-text-form">Mức lương cơ bản</div>
                            <input type="text" class="input width-100 m-salary">
                        </div>
                    </div>

                    <div class="m-joindate-workstatus m-display-98 mt-10">
                        <div class="m-container">
                            <div class="m-text-form">Ngày gia nhập công ty</div>
                            <input type="date" class="input width-100 m-joindate">

                        </div>
                       <div class="m-container">
                            <div class="m-text-form">Tình trạng công việc</div>
                            <div class="m-combobox m-combobox-workstatus">
                                <input class="m-show-combobox" readonly="readonly" placeholder="Chọn thông tin">
                                <button class="m-icon-combobox">
                                    <div class="m-icon-dropdown"></div>
                                </button>
                            </div>
                        </div>
                    </div>

                </div>
            </div>

            <div class="m-bottom-form-add">
                <div class="btn btn-close">Hủy</div>
                <div class="btn btn-icon m-icon-save btn-save">Lưu</div>
            </div>
            

        </div>
    </div>
</template>

<script>
   
    export default {
        methods:{

            /**
             * Author: NVHThai (26/08/2022)
             * Ẩn form thêm nhân viên
             */
            btnCloseFormAddOnclick(){

                /**
                 * emit là hàm để gọi vào hàm cha
                 * isShowDialog khai báo bên hàm cha @isShowDialog
                 */
                this.$emit("isShowDialog", false);
            }
        },

        props: ['isShow'],

        data(){
            return {
                    
            }
        },

    }
</script>

<style scoped>

</style>