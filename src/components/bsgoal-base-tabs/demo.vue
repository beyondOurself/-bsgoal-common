<!--
 * @Author: canlong.shen
 * @Date: 2023-04-28 16:01:11
 * @LastEditors: canlong.shen
 * @LastEditTime: 2023-06-01 11:03:24
 * @FilePath: \common\src\components\bsgoal-base-tabs\demo.vue
 * @Description: tabs 标签切页 公共组件演示
-->
<script setup>
/* setup模板
---------------------------------------------------------------- */
import { ref } from 'vue'
import BsgoalBaseTabs from './index.vue'

defineOptions({
  name: 'BsgoalBaseTabsDemo'
})

const props = defineProps({})
const activeTabName = ref('tab1')
const config = ref([
  {
    label: 'tab1',
    value: 'tab1'
  },
  {
    label: 'tab2',
    value: 'tab2'
  },
  {
    label: 'tab3',
    value: 'tab3'
  },
  {
    label: 'tab4',
    value: 'tab4'
  }
])
</script>
<template>
  <div class="bsgoal-base-tabs-demo">
    <div class="base_tabs_demo">
      <BsgoalBaseTabs :config-options="config" stretch fill>
        <template #tab1>
          <div>这是 tab1</div>
        </template>
      </BsgoalBaseTabs>
    </div>
  </div>
</template>
<style lang="scss" scoped>
/* 自定义样式
---------------------------------------------------------------- */
.base_tabs_demo {
  position: absolute;
  top: 0;
  bottom: 0;
  right: 0;
  left: 0;
}
</style>
<style lang="scss">
/* 覆盖样式
---------------------------------------------------------------- */
</style>
