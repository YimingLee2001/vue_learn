<template>
  <div @click="handleFullScreen" id="screenFull">
    <el-icon v-if="!isFull"><FullScreen /></el-icon>
    <el-icon v-else><Crop /></el-icon>
  </div>
</template>
<script setup>
import screenfull from 'screenfull'
import { ref, onMounted, onBeforeMount } from 'vue'

const isFull = ref(screenfull.isFullscreen)
const handleFullScreen = () => {
  if (screenfull.isEnabled) {
    screenfull.toggle()
  }
}

const changeIcon = () => {
  isFull.value = screenfull.isFullscreen
}
onMounted(() => {
  screenfull.on('change', changeIcon)
})
onBeforeMount(() => {
  screenfull.off('change')
})
</script>
<style lang="scss" scoped></style>
