<template>
  <div>
    <t-search v-model="value" :clearable="true" placeholder="请输入关键字" @change="onChange"></t-search>
  </div>
</template>

<script lang="ts">
import { defineComponent, ref } from 'vue';

export default defineComponent({
  setup() {
    const onChange = (val: string) => {
      console.log('change: ', val);
    };

    const value = ref('');

    return {
      onChange,
      value,
    };
  },
});
</script>
