<template>
  <div>
    <div class="tdesign-mobile-demo">
      <h1 class="title">Checkbox 多选框</h1>
      <p class="summary">描述文字</p>
      <tdesign-demo-block title="01 类型" summary="基础多选框">
        <t-check-group v-model:value="checkBoxs1" @change="changeFn">
          <t-cell-group>
            <t-cell>
              <template #leftIcon>
                <t-checkbox name="checkbox1" value="1"></t-checkbox>
              </template>
              <template #title>
                <span>多选</span>
              </template>
            </t-cell>
            <t-cell>
              <template #leftIcon>
                <t-checkbox name="checkbox1" value="2" :icon="circleFilledIcons"></t-checkbox>
              </template>
              <template #title>
                <span>多选</span>
              </template>
            </t-cell>
            <t-cell>
              <template #leftIcon>
                <t-checkbox name="checkbox1" value="3" :icon="circleFilledIcons"></t-checkbox>
              </template>
              <template #title>
                <span>多选</span>
              </template>
            </t-cell>
            <t-cell>
              <template #leftIcon>
                <t-checkbox name="checkbox1" value="4" :icon="circleFilledIcons"></t-checkbox>
              </template>
              <template #title>
                <span>
                  多选多选多选多选多选多选多选多选多选多选多选多选多选多选多选多选多选
                  多选多选多选多选多选多选多选多选多选多选多选多选多选多选多选多选多选多选多选多选
                  多选多选多选多选多选多选多选多选多选多选多选多选多选多选多选
                </span>
              </template>
            </t-cell>
            <t-cell>
              <template #leftIcon>
                <t-checkbox name="checkbox1" value="5" :icon="circleFilledIcons"></t-checkbox>
              </template>
              <template #title>
                <span>多选</span>
              </template>
              <template #description>
                <span
                  >多选多选多选多选多选多选多选多选多选多选多选多选多选多选多选
                  多选多选多选多选多选多选多选多选多选多选多选
                </span>
              </template>
            </t-cell>
          </t-cell-group>
        </t-check-group>
      </tdesign-demo-block>
      <tdesign-demo-block summary="右侧圆形多选框">
        <t-cell-group>
          <t-cell>
            <template #rightIcon>
              <t-checkbox name="checkbox2" value="1" checked :icon="circleFilledIcons"></t-checkbox>
            </template>
            <template #title>
              <span>多选</span>
            </template>
          </t-cell>
          <t-cell>
            <template #rightIcon>
              <t-checkbox name="checkbox2" value="2" checked :icon="circleFilledIcons"></t-checkbox>
            </template>
            <template #title>
              <span>多选</span>
            </template>
          </t-cell>
          <t-cell>
            <template #rightIcon>
              <t-checkbox name="checkbox2" value="3" :icon="circleFilledIcons"></t-checkbox>
            </template>
            <template #title>
              <span>多选</span>
            </template>
          </t-cell>
          <t-cell>
            <template #rightIcon>
              <t-checkbox name="checkbox2" value="4" :icon="circleFilledIcons"></t-checkbox>
            </template>
            <template #title>
              <span
                >多选多选多选多选多选多选多选多选多选多选多选多选多选多选多选多选多选多选多选多选多选多选多选多选多选多选多选多选多选多选多选多选多选多选多选多选多选多选多选多选多选多选多选多选多选多选多选多选多选多选多选多选</span
              >
            </template>
          </t-cell>
        </t-cell-group>
      </tdesign-demo-block>
      <tdesign-demo-block summary="带全选多选框">
        <t-check-group v-model="checkBoxs2">
          <t-cell-group>
            <t-cell>
              <template #leftIcon>
                <t-checkbox name="checkbox1" :check-all="true"></t-checkbox>
              </template>
              <template #title>
                <span>全选</span>
              </template>
            </t-cell>
            <t-cell>
              <template #leftIcon>
                <t-checkbox name="checkbox2" value="1"></t-checkbox>
              </template>
              <template #title>
                <span>多选</span>
              </template>
            </t-cell>
            <t-cell>
              <template #leftIcon>
                <t-checkbox name="checkbox3" value="2"></t-checkbox>
              </template>
              <template #title>
                <span>多选</span>
              </template>
            </t-cell>
            <t-cell>
              <template #leftIcon>
                <t-checkbox name="checkbox4" value="3"></t-checkbox>
              </template>
              <template #title>
                <span>多选</span>
              </template>
            </t-cell>
          </t-cell-group>
        </t-check-group>
      </tdesign-demo-block>
      <tdesign-demo-block title="02 状态" summary="多选框禁用态">
        <t-check-group v-model:value="checkBoxs3">
          <t-cell-group>
            <t-cell>
              <template #leftIcon>
                <t-checkbox name="checkbox4" value="1" :icon="circleFilledIcons" disabled></t-checkbox>
              </template>
              <template #title>
                <span style="color: rgba(0, 0, 0, 0.26)">多选</span>
              </template>
            </t-cell>
            <t-cell>
              <template #leftIcon>
                <t-checkbox name="checkbox4" value="2" :icon="circleFilledIcons" disabled></t-checkbox>
              </template>
              <template #title>
                <span style="color: rgba(0, 0, 0, 0.26)">多选</span>
              </template>
            </t-cell>
          </t-cell-group>
        </t-check-group>
        <t-cell-group>
          <t-cell>
            <template #rightIcon>
              <t-checkbox name="checkbox4" value="3" checked :icon="circleFilledIcons" disabled></t-checkbox>
            </template>
            <template #title>
              <span style="color: rgba(0, 0, 0, 0.26)">多选</span>
            </template>
          </t-cell>
          <t-cell>
            <template #rightIcon>
              <t-checkbox name="checkbox4" value="4" :icon="circleFilledIcons" disabled></t-checkbox>
            </template>
            <template #title>
              <span style="color: rgba(0, 0, 0, 0.26)">多选</span>
            </template>
          </t-cell>
        </t-cell-group>
      </tdesign-demo-block>
      <tdesign-demo-block summary="多选框半选态">
        <t-check-group>
          <t-cell-group>
            <t-cell>
              <template #leftIcon>
                <t-checkbox name="checkbox5" :checked="true" :indeterminate="true"></t-checkbox>
              </template>
              <template #title>
                <span>半选</span>
              </template>
            </t-cell>
          </t-cell-group>
        </t-check-group>
      </tdesign-demo-block>
      <tdesign-demo-block title="03 特殊类型" summary="自定义图标多选框">
        <t-check-group v-model="checkBoxs2">
          <t-cell-group>
            <t-cell>
              <template #leftIcon>
                <t-checkbox name="checkbox6" value="1" :icon="CheckRectangleFilledIcons"></t-checkbox>
              </template>
              <template #title>
                <span>多选</span>
              </template>
            </t-cell>
            <t-cell>
              <template #leftIcon>
                <t-checkbox name="checkbox6" value="2" :icon="CheckRectangleFilledIcons"></t-checkbox>
              </template>
              <template #title>
                <span>多选</span>
              </template>
            </t-cell>
            <t-cell>
              <template #leftIcon>
                <t-checkbox name="checkbox6" value="3" :icon="CheckRectangleFilledIcons"></t-checkbox>
              </template>
              <template #title>
                <span>多选</span>
              </template>
            </t-cell>
          </t-cell-group>
        </t-check-group>
      </tdesign-demo-block>
      <tdesign-demo-block title="04 规格" summary="多选框尺寸规格">
        <t-cell-group>
          <t-cell>
            <template #title>
              <t-checkbox name="checkbox7" :checked="true">多选 H48</t-checkbox>
            </template>
          </t-cell>
        </t-cell-group>
      </tdesign-demo-block>
      <tdesign-demo-block style="margin-top: 16px">
        <t-cell-group>
          <t-cell style="height: 56px">
            <template #title>
              <t-checkbox name="checkbox7" :checked="true">多选 H56</t-checkbox>
            </template>
          </t-cell>
        </t-cell-group>
      </tdesign-demo-block>
    </div>
  </div>
</template>
<script lang="ts">
import { ref, watch, defineComponent, h } from 'vue';
import { CheckCircleFilledIcon, CircleIcon, CheckRectangleFilledIcon, RectangleIcon } from 'tdesign-icons-vue-next';

export default defineComponent({
  setup() {
    const checkBoxs1 = ref(['1', '3']);
    const checkBoxs2 = ref(['2', '3']);
    const checkBoxs3 = ref(['1', '4']);
    const checkBoxs4 = ref(['1', '4']);
    const indeterminate = ref(false);
    watch(
      () => checkBoxs1.value,
      (val) => {
        console.log('checkBoxs1:', val);
      },
    );

    // watch(
    //   () => checkBoxs2.value,
    //   (val) => {
    //     indeterminate.value = val.length < 4;
    //     console.log('checkBoxs2:', val.length);
    //   },
    // );

    const TIconCircleFilled = h(CheckCircleFilledIcon);
    const TIconCircle = h(CircleIcon);
    const TCheckRectangleFilledIcon = h(CheckRectangleFilledIcon);
    const TRectangleIcon = h(RectangleIcon);
    const changeFn = (value: any, context: { e: Event }) => {
      console.log('value:', value);
      console.log('Event:', context);
    };

    const checkboxChange = (val: boolean) => {
      console.log('val:', val);
    };

    return {
      checkBoxs1,
      checkBoxs2,
      checkBoxs3,
      checkBoxs4,
      circleFilledIcons: [TIconCircleFilled, TIconCircle],
      CheckRectangleFilledIcons: [TCheckRectangleFilledIcon, TRectangleIcon],
      changeFn,
      checkboxChange,
      indeterminate,
    };
  },
});
</script>
<style lang="less" scoped>
.select {
  font-size: 16px;
  display: inline-block;
  width: 50px;
  text-align: center;
  border-radius: 2px;
  color: #ffffff;
}
.select-all {
  background-color: #0052d9;
}
.canle-all {
  background-color: #07c160;
  margin-left: 20px;
}
</style>
