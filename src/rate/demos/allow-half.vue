<template>
  <t-rate v-model="value" allow-half />
</template>

<script lang="ts">
import { defineComponent, ref } from 'vue';

export default defineComponent({
  setup() {
    return {
      value: ref(3.5),
    };
  },
});
</script>
