<script setup>
import { ref } from "vue";
import AgentCard from "./AgentCard.vue";

const response = ref({});
const url = "https://valorant-api.com/v1/agents";

await new Promise(async (resolve) => {
  setTimeout(() => {
    resolve();
  }, 1000);

  try {
    const res = await fetch(url);
    console.log(res);
    response.value = await res.json();
  } catch (error) {
    response.value = "error! could not reach the api";
  }
});

console.log("this is the json response", response.value);
</script>

<template>
  <AgentCard v-for="(item, index) in response.data" :key="`${index}`">
    <h1>{{ item.displayName }}<br /></h1>
    <p id="description">{{ item.description }}</p>
    <img :src="item.fullPortrait" alt="Valorant image" />
  </AgentCard>
</template>

<style scoped>
h1 {
  color: black;
  font-family: Arial, Helvetica, sans-serif;
  text-align: center;
  padding-top: 10px;
}

#description {
  font-family: Arial, Helvetica, sans-serif;
  opacity: 0.8;
  width: 350px;
  margin: 0 auto;
}

img {
  position: absolute;
  width: 300px;
  height: 300px;
  top: 140px;
  left: 70px;
}
</style>
