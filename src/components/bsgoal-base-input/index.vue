<!--
 * @Author: canlong.shen
 * @Date: 2023-05-29 09:38:52
 * @LastEditors: canlong.shen
 * @LastEditTime: 2023-05-29 18:01:19
 * @FilePath: \common\src\components\bsgoal-base-input\index.vue
 * @Description:  Input 输入框
 * 
-->

<script setup>
/* setup模板
---------------------------------------------------------------- */
import { processSlotOutlet } from '@vue/compiler-core'
import { ref, watch, watchEffect } from 'vue'

defineOptions({
  name: 'BsgoalBaseInput'
})

const props = defineProps({
  /**
   * value
   */
  modelValue: {
    type: [String, Number],
    default: ''
  },
  /**
   * placeholder
   */
  placeholder: {
    type: [String],
    default: '请输入'
  },
  /**
   * 禁用状态
   */
  disabled: {
    type: [Boolean],
    default: false
  },
  /**
   * 输入值格式
   */
  formatter: {
    type: [Function],
    default: () => {
      return (v) => v
    }
  },
  /**
   * 提取值
   */
  parser: {
    type: [Function],
    default: () => {
      return (v) => v
    }
  }
})

const emits = defineEmits(['update:modelValue', 'change'])

// ---> S 值绑定 <---

const inputValue = ref('')

watchEffect(() => {
  inputValue.value = props.modelValue
})

// ---> E 值绑定 <---

// ---> S 事件  <---

/**
 * @Author: canlong.shen
 * @description: 触发 变动输入
 * @default:
 * @return {*}
 */
const change = (value = '') => {
  emits('change', value)
  emits('update:modelValue', value)
}
/**
 * @Author: canlong.shen
 * @description: 触发 清空输入
 * @default:
 * @return {*}
 */
const clear = (value = '') => {
  emits('clear', value)
  emits('update:modelValue', value)
}
/**
 * @Author: canlong.shen
 * @description: 触发 输入事件
 * @default:
 * @return {*}
 */
const input = (value = '') => {
  emits('input', value)
  emits('update:modelValue', value)
}

// ---> E 事件  <---
</script>

<template>
  <div class="bsgoal-base-input">
    <el-input
      v-model="inputValue"
      clearable
      class="base_input"
      :placeholder="placeholder"
      :disabled="disabled"
      :formatter="formatter"
      :parser="parser"
      @change="change"
      @clear="clear"
      @input="input"
    />
  </div>
</template>
<style lang="scss" scoped>
/* 自定义样式
---------------------------------------------------------------- */
</style>
<style lang="scss">
/* 覆盖样式
---------------------------------------------------------------- */
</style>
