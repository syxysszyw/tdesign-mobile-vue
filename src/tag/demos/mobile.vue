<template>
  <div class="tdesign-mobile-demo">
    <h1 class="title">Tag 标签</h1>
    <p class="summary">用于标记表示主体属性、类型、状态等，由底部图形和标签文字组成</p>
    <tdesign-demo-block title="01 类型" summary="展示型标签">
      <div class="tag-demo">
        <t-tag theme="primary">标签</t-tag>
        <t-tag theme="danger">标签</t-tag>
        <t-tag theme="warning">标签</t-tag>
        <t-tag theme="success">标签</t-tag>
        <t-tag theme="default">标签</t-tag>
      </div>
      <div class="tag-demo">
        <t-tag theme="primary" variant="dark">标签</t-tag>
        <t-tag theme="primary" variant="light">标签</t-tag>
        <t-tag theme="primary" variant="outline">标签</t-tag>
        <t-tag theme="primary" variant="light-outline">标签</t-tag>
      </div>
      <div class="tag-demo">
        <t-tag theme="primary" shape="round">标签</t-tag>
        <t-tag theme="primary" shape="mark">标签</t-tag>
      </div>
    </tdesign-demo-block>
    <tdesign-demo-block summary="点击型标签">
      <div class="tag-demo">
        <t-tag
          v-for="(tag, index) in closableTags"
          :key="tag"
          closable
          theme="primary"
          :size="tag.size"
          @close="onClickClose(index)"
          >{{ tag.name }}</t-tag
        >
      </div>
    </tdesign-demo-block>
    <tdesign-demo-block title="02 状态" summary="标签状态">
      <div class="tag-demo">
        <t-check-tag :checked="checkedTag">已点击</t-check-tag>
        <t-check-tag :default-checked="false">未点击</t-check-tag>
        <t-check-tag disabled>不可点击</t-check-tag>
      </div>
    </tdesign-demo-block>
    <tdesign-demo-block title="03 规格" summary="标签规格">
      <div class="tag-demo">
        <t-tag size="large" theme="primary">大号</t-tag>
        <t-tag size="medium" theme="primary">中号</t-tag>
        <t-tag size="small" theme="primary">小号</t-tag>
      </div>
    </tdesign-demo-block>
  </div>
</template>

<script lang="ts">
import { ref, defineComponent } from 'vue';

export default defineComponent({
  setup() {
    const checkedTag = ref(true);
    const closableTags = ref([
      {
        name: '标签',
        size: 'large',
      },
      {
        name: '标签',
      },
    ]);

    function onClickClose(index: number) {
      console.log(index);
      closableTags.value.splice(index, 1);
    }

    return {
      closableTags,
      onClickClose,
      checkedTag,
    };
  },
});
</script>
