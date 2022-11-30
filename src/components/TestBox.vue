<script setup>
const props = defineProps({
  name: {
    type: String,
    default: "",
  },
  updateName: {
    type: Function,
    default: () => {},
  },
});

const emit = defineEmits(["change-name"]);
const changeName = () => {
  emit("change-name", "Robert");
};
</script>
<template>
  <div>
    <h1>{{ props.name }}</h1>
    <!-- ----------Example5---------- -->
    <!-- <button @click="changeName">change name</button> -->

    <!-- ----------Example6---------- -->
    <button @click="props.updateName('Robert')">change name</button>
  </div>
</template>
