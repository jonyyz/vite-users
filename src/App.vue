<template>
  <users :value="users" />
</template>

<script setup>
import { onMounted, ref } from "vue";
import Users from "./components/users.vue";

const users = ref([]);

onMounted(async () => {
  const response = await fetch("https://jsonplaceholder.typicode.com/users");
  users.value = await response.json();
});
</script>
