<script setup>
import { ref } from "vue";
const response = ref({});

await new Promise(async (resolve) => {
  setTimeout(() => {
    resolve();
  }, 1000);

  try {
    const res = await fetch(" https://randomfox.ca/floof/");
    console.log(res);
    response.value = await res.json();
  } catch (error) {
    response.value = "error! could not reach the api";
  }
});

console.log(response.value);
</script>

<template>
  <img :src="response.image" alt="fox image" />
</template>

<style scoped>
img {
  width: 350px;
  height: 250px;
}
</style>
