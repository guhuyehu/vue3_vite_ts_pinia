<template>
  <div>用户名:{{ mainStore.name }}<br />长度:{{ mainStore.nameLength }}</div>
  <hr />
  <button @click="updateName">修改store中的name</button>
  <hr />
  <TestUI />
</template>

<script setup lang="ts">
import { useMainStore } from "@/store/main";
import TestUI from "@/components/TestUI.vue";

const mainStore = useMainStore();
console.log(import.meta.env.VITE_APP_WEB_URL);
const updateName = () => {
  // $patch 修改 store 中的数据
  mainStore.$patch({
    name: "名称被修改了,nameLength也随之改变了",
  });
};
</script>
