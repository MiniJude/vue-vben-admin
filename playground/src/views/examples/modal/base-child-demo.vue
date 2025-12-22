<script lang="ts" setup>
import { useVbenModal } from '@vben/common-ui';

import { Button } from 'ant-design-vue';

const [Modal, modalApi] = useVbenModal({
  destroyOnClose: true,
});

function openNestedModal() {
  modalApi.open();
}
</script>
<template>
  <div>
    <Button @click="openNestedModal" type="primary">打开子弹窗</Button>
    <Modal class="w-[400px]" title="基础弹框">
      bug：当关闭这个弹框时，父弹框也会被关闭！！
    </Modal>
  </div>
</template>
