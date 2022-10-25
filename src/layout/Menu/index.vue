<template lang="">
  <el-menu
    active-text-color="$menuActiveText"
    background-color="$menuBg"
    class="el-menu-vertical-demo"
    default-active="2"
    text-color="#fff"
    router
  >
    <el-sub-menu :index="item.id" v-for="item in menusList" :key="item.id">
      <template #title>
        <span>{{ item.authName }}</span>
      </template>
      <el-menu-item
        :index="'/' + it.path"
        v-for="it in item.children"
        :key="it.id"
        >{{ it.authName }}</el-menu-item
      >
    </el-sub-menu>
  </el-menu>
</template>
<script setup>
import { menuList } from '@/api/menu'
import { ref } from 'vue'

const menusList = ref([])
const initMenusList = async () => {
  menusList.value = await menuList()
  //   console.log(res)
}
initMenusList()
</script>
<style lang=""></style>
