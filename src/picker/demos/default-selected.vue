<template>
  <div class="tdesign-demo-block">
    <t-picker title="标题" @change="onChange" @confirm="onConfirm" @cancel="onCancel">
      <t-picker-item :options="roleOptions" :default-index="2" @change="onColumnChange" />
    </t-picker>
  </div>
</template>

<script lang="ts">
import { ref, defineComponent } from 'vue';

export default defineComponent({
  setup() {
    const roles = ['战士', '法师', '射手', '刺客', '坦克', '辅助'];
    const curRoleIndex = ref(0);
    const roleOptions = ref(roles);

    const onColumnChange = (e: any) => {
      console.log('column:change', e);
    };

    const onRoleChange = (e: any) => {
      console.log('column:change', e);
      curRoleIndex.value = e.index;
    };

    const onChange = (e: any) => {
      console.log('picker:change', e);
    };

    const onConfirm = (e: any) => {
      console.log('picker:confirm', e);
    };

    const onCancel = () => {
      console.log('取消');
    };

    return {
      roleOptions,
      onColumnChange,
      onRoleChange,
      onChange,
      onConfirm,
      onCancel,
    };
  },
});
</script>
