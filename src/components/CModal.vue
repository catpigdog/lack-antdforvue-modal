<script lang="ts" setup>
import { useAttrs } from 'vue'
import { Modal, type ModalProps } from 'ant-design-vue'


// ModalProps不具有onUpdate:open属性
// 以下是封装Modal的使用场景

const attrs = useAttrs() as ModalProps
const confirm = () => {
  // ...
  // ...

  // 关闭弹窗
  attrs['onUpdate:open']?.(false)  // ts报错ModalProps中缺少onUpdate:open 属性
  // 有onUpdate:visible参数但，ant-design-vue下个版本会删除visible(v-model)参数不建议使用
}
</script>

<template>
  <Modal>
    <div>业务展示...</div>
    <template #footer>
      <button @click="confirm">完成</button>
    </template>
  </Modal>
</template>
