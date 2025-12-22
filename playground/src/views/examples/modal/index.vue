<script lang="ts" setup>
import { onBeforeUnmount } from 'vue';

import { clearAllAlerts, Page, useVbenModal } from '@vben/common-ui';

import { Button, Card, Flex } from 'ant-design-vue';

import DocButton from '../doc-button.vue';
import NestedDemo from './nested-demo.vue';

defineOptions({ name: 'ModalExample' });

const [NestedModal, nestedModalApi] = useVbenModal({
  connectedComponent: NestedDemo,
  destroyOnClose: true,
});

function openNestedModal() {
  nestedModalApi.open();
}

onBeforeUnmount(() => {
  // 清除所有弹窗
  clearAllAlerts();
});
</script>

<template>
  <Page
    auto-content-height
    description="弹窗组件常用于在不离开当前页面的情况下，显示额外的信息、表单或操作提示，更多api请查看组件文档。"
    title="弹窗组件示例"
  >
    <template #extra>
      <DocButton path="/components/common-ui/vben-modal" />
    </template>
    <NestedModal />
    <Flex wrap="wrap" class="w-full" gap="10">
      <Card class="w-[300px]" title="嵌套弹窗示例">
        <p>
          复现
          <a href="https://github.com/vbenjs/vue-vben-admin/pull/7035">
            #7035
          </a>
          中描述的问题
        </p>
        <template #actions>
          <Button type="primary" @click="openNestedModal">打开嵌套弹窗</Button>
        </template>
      </Card>
    </Flex>
  </Page>
</template>
