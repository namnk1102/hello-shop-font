<script setup>
import TableProduct from "~/components/manage/TableProduct.vue";

definePageMeta({
    layout: "admin",
    middleware: "auth"
})

import TableOrder from "~/components/manage/TableOrder.vue";
import TableUser from "~/components/manage/TableUser.vue";

const active = ref('1')

const handleChange = (key) => {
    console.log(key)
    active.value = key
}
</script>

<template>
    <div class="w-full h-screen">
        <div class="w-full h-full flex">
            <el-menu
                active-text-color="#ffd04b"
                background-color="#000"
                default-active="1"
                text-color="#fff"
                class="w-60 h-full"
                @select="handleChange"
            >
                <el-menu-item class="mb-6" index="0">
                    <img class="h-32 mt-8 ml-6"
                         src="https://1.bp.blogspot.com/-R8gnX_mf-hI/XZwpsZoVyNI/AAAAAAAADOc/zfTGRKC1VyUVP2hxELrNk04TJTrHDg0mQCLcBGAsYHQ/s0/72487982_2513824035518413_4387733843654737920_n.png"
                         alt="">
                </el-menu-item>
                <el-menu-item index="1">
                    <span>Quản lý sản phẩm</span>
                </el-menu-item>
                <el-menu-item index="2">
                    <span>Quản lý đơn hàng</span>
                </el-menu-item>
                <el-menu-item index="3">
                    <span>Quản lý tài khoản</span>
                </el-menu-item>
            </el-menu>
            <TableProduct v-if="active === '1'" class="flex-1 overflow-auto"/>
            <TableOrder v-if="active === '2'" class="flex-1 overflow-auto"/>
            <TableUser v-if="active === '3'" class="flex-1 overflow-auto"/>
        </div>
    </div>
</template>

<style lang="scss">

</style>