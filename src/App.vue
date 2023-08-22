<script setup lang="ts">
import { ref } from 'vue'
import CModal from './components/CModal.vue'

const open = ref(false)

</script>

<template>
  <div>
    <button @click="open = true">打开业务弹窗</button>
    <CModal v-model:open="open"></CModal>
  </div>
</template>
