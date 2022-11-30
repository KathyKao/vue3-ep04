<script setup>
// 使用 v-model 預設會存在 modelValue 的 props
// v-model 是個語法糖, 包含 props 和 emit input 事件
const props = defineProps(["modelValue"]);
const emit = defineEmits(["update:modelValue"]);
</script>
<template>
  <div>
    <input
      type="text"
      :value="props.modelValue"
      @input="emit('update:modelValue', $event.target.value)"
    />
  </div>
</template>
