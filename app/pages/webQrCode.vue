<script lang="ts" setup>
import { renderSVG } from 'uqr'
import { ref, onMounted } from 'vue'

// 定义响应式变量
const qrCodeSVG = ref<string | null>(null) 
const url = 'https://qrs-xi.vercel.app/scan' 

onMounted(async () => {
  try {
    qrCodeSVG.value = await renderSVG(url)
  } catch (err) {
    console.error('二维码生成失败:', err)
  }
})
</script>

<template>
  <div
    class="aspect-square [&>svg]:h-full [&>svg]:w-full"
    h-full w-full overflow-hidden rounded="~ sm:lg"
    v-html="qrCodeSVG"
  />
</template>