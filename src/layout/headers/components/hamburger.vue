<template>
  <div class="hamburger-container" @click="toggleClick">
    <el-icon v-if="siderState"><Fold /></el-icon>
    <el-icon v-else><Expand /></el-icon>
  </div>
</template>

<script setup>
// import store from '@/store'
import { useStore } from 'vuex'
import { computed } from 'vue'

const store = useStore()
const siderState = computed(() => {
  return store.getters.siderType
})
const toggleClick = () => {
  store.commit('app/changeSiderType')
}
</script>

<style lang="scss">
.hamburger-container {
  margin-right: 16px;
  box-sizing: border-box;
  cursor: pointer;
}
</style>
