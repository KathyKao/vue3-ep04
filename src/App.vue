<script setup>
import { ref, watch } from "vue";
import InputBar from "./components/InputBar.vue";
import TestBox from "./components/TestBox.vue";

// ----------Example1----------
// // v-model 雙向綁定
// const name = ref("Kathy");
// const setName = (str) => {
//   name.value = str;
// };

// ----------Example2----------
// // v-model Modifiers 修飾符
// const name = ref("Kathy");

// ----------Example3----------
// // v-model Modifiers 修飾符
// const num = ref("123");
// watch(num, (newVal) => {
//   console.log(newVal);
// });

// ----------Example4----------
// // 自定義組件並使用 v-model
// const num = ref("123");

// ----------Example5----------
// // 自定義組件, 父層 props 資料到子層, 子層 emit 方法給父層修改資料
// const name = ref("Kathy");
// const updateName = (newName) => {
//   name.value = newName;
// };

// ----------Example6----------
// 自定義組件, 透過 props 傳遞 function 到子層去執行 function, 而不是子層直接修改 props 傳下來的資料
// One-Way Data Flow(單向資料流)
const name = ref("Kathy");
const updateName = (newName) => {
  name.value = newName;
};
</script>

<template>
  <!-- ----------Example1---------- -->
  <!-- <div><input type="text" v-model="name" /></div>
  {{ name }}
  <button @click="setName('Robert')">click</button> -->

  <!-- ----------Example2---------- -->
  <!-- <div><input type="text" v-model.lazy="name" /></div>
  {{ name }} -->

  <!-- ----------Example3---------- -->
  <!-- <div><input type="text" v-model.number="num" /></div>
  {{ num }} -->

  <!-- ----------Example4---------- -->
  <!-- <InputBar v-model="num" />
  {{ num }} -->

  <!-- ----------Example5---------- -->
  <!-- <TestBox :name="name" @change-name="updateName" /> -->

  <!-- ----------Example6---------- -->
  <TestBox :name="name" :update-name="updateName" />
</template>

<style scoped></style>
