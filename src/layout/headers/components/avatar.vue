<template>
  <el-dropdown>
    <span class="el-dropdown-link">
      <el-avatar shape="square" :size="40" :src="squareUrl" />
    </span>
    <template #dropdown>
      <el-dropdown-menu>
        <el-dropdown-item @click="logout">退出</el-dropdown-item>
      </el-dropdown-menu>
    </template>
  </el-dropdown>
</template>
<script setup>
import { ref } from 'vue'
import { useStore } from 'vuex'

const squareUrl = ref(
  'https://tse4-mm.cn.bing.net/th/id/OIP-C.hqD6F7mzf_dRi1UuJRegrgAAAA?w=194&h=194&c=7&r=0&o=5&dpr=1.3&pid=1.7'
)
const store = useStore()
const logout = () => {
  store.dispatch('app/logout')
}
</script>
<style lang="scss">
::v-deep(.el-dropdown-menu__item) {
  white-space: nowrap;
}
</style>
