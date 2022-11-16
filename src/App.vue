<script setup>
// This starter template is using Vue 3 <script setup> SFCs
// Check out https://vuejs.org/api/sfc-script-setup.html#script-setup
import ValorantAgents from "./components/ValorantAgents.vue";
</script>

<template>
  <div>
    <h1>Welcome to Valorant agent newspaper</h1>
    <CatList />
    <Suspense>
      <ValorantAgents />
      <template #fallback>
        <p>Loading....</p>
      </template>
    </Suspense>
  </div>
</template>

<style scoped>
h1 {
  color: black;
  font-size: 35px;
  font-family: "Times New Roman", Times, serif;
  text-align: center;
}
</style>
