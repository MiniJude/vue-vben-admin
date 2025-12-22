<script lang="ts" setup>
import { useVbenModal } from '@vben/common-ui';

import BaseChildDemo from './base-child-demo.vue';

const [Modal] = useVbenModal({
  destroyOnClose: true,
});
</script>
<template>
  <Modal title="嵌套弹窗示例">
    <BaseChildDemo />
  </Modal>
</template>
