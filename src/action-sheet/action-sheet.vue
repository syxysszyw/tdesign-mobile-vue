<template>
  <t-popup :class="name" :visible="currentVisible" placement="bottom" @close="handleClose">
    <div :class="rootClasses">
      <!-- @ts-ignore -->
      <menu-list v-if="type === 'list'" :items="actionItems" @selected="handleSelected">
        <template #cell="slotProps">
          <slot name="cell" :item="slotProps.item"></slot>
        </template>
      </menu-list>

      <menu-grid v-else :items="actionItems" :count="count" @selected="handleSelected">
        <template #cell="slotProps">
          <slot name="cell" :item="slotProps.item"></slot>
        </template>
      </menu-grid>

      <template v-if="showCancel">
        <div v-if="type === 'list'" :class="`${name}__separation`"></div>
        <button :class="`${name}__action`" @click="handleCancel">{{ cancelText }}</button>
      </template>
    </div>
  </t-popup>
</template>

<script lang="ts">
import { ref, computed, watch, defineComponent, PropType, ComputedRef, SetupContext } from 'vue';
import { useEmitEvent } from '../shared';
import MenuList from './menu-list.vue';
import MenuGrid from './menu-grid.vue';
import TPopup from '../popup';
import config from '../config';
import { ActionSheetItem } from './type';

const { prefix } = config;
const name = `${prefix}-action-sheet`;

export default defineComponent({
  name,
  components: {
    TPopup,
    MenuList,
    MenuGrid,
  },
  props: {
    modelValue: Boolean,
    /**
     * @description 是否显示
     * @attribute visible
     */
    visible: {
      type: Boolean,
      default: false,
    },
    /**
     * @description 菜单项
     * @attribute items
     */
    items: {
      type: Array as PropType<Array<ActionSheetItem | string>>,
      required: true,
    },
    /**
     * @description 展示类型
     * @attribute type
     */
    type: {
      type: String,
      default: 'list',
    },
    /**
     * @description grid时每页显示的数量
     * @attribute count
     */
    count: {
      type: Number,
      default: 8,
    },
    /**
     * @description 是否展示【取消】选项
     * @attribute show-cancel
     */
    showCancel: {
      type: Boolean,
      default: true,
    },
    /**
     * @description 【取消】选项的文本
     * @attribute cancel-text
     */
    cancelText: {
      type: String,
      default: '取消',
    },
  },
  emits: ['selected', 'update:modelValue', 'cancel', 'close'],
  setup(props, context: SetupContext) {
    const emitEvent = useEmitEvent(props, context.emit);
    const actionItems = ref([]);

    const currentVisible = computed(() => props.modelValue || props.visible) as ComputedRef<boolean>;
    const rootClasses = computed(() => ({
      [`${name}__panel`]: true,
      [`${name}__panel-list`]: props.type === 'list',
      [`${name}__panel-grid`]: props.type === 'grid',
    }));

    watch(
      () => props.items,
      (val) => {
        let items = JSON.parse(JSON.stringify(val));
        // 数据格式处理，统一转为object结构
        items = items.map((item: unknown) => {
          if (typeof item === 'string') {
            return { label: item };
          }

          return item;
        });
        actionItems.value = items;
      },
      {
        immediate: true,
        deep: true,
      },
    );

    const handleCancel = () => {
      emitEvent('cancel');
      context.emit('update:modelValue', false);
    };

    const handleSelected = (index: number) => {
      emitEvent('selected', props.items[index], index);
    };

    const handleClose = () => {
      emitEvent('close');
      context.emit('update:modelValue', false);
    };

    return {
      name: ref(name),
      rootClasses,
      actionItems,
      currentVisible,
      handleCancel,
      handleSelected,
      handleClose,
    };
  },
});
</script>
