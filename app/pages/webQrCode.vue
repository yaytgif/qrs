<script lang="ts" setup>
import { renderSVG } from 'uqr'
import { onMounted, ref } from 'vue'

// 定义响应式变量
const qrCodeSVG = ref<string | null>(null)
const url = 'https://qrs-xi.vercel.app/scan'

onMounted(() => {
  try {
    qrCodeSVG.value = renderSVG(url)
  }
  catch (err) {
    console.error('二维码生成失败:', err)
  }
})
</script>

<template>
  <div>
    <div class="ml-5% font-size-4 color-#f39c12">
      {{ $t('webScanCodeTips') }}
    </div>
    <div
      class="ml-5% aspect-square [&>svg]:h-full [&>svg]:w-90%"
      h-full w-full overflow-hidden rounded="~ sm:lg"
      v-html="qrCodeSVG"
    />
  </div>
</template>
