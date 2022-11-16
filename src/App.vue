<script setup>
// This starter template is using Vue 3 <script setup> SFCs
// Check out https://vuejs.org/api/sfc-script-setup.html#script-setup
import RandomFox from "./components/RandomFox.vue";
</script>

<template>
  <div>
    <h1>This page shows random picture of foxs</h1>
    <CatList />
    <Suspense>
      <RandomFox />
      <template #fallback>
        <img src="https://media.tenor.com/o8m3bKTsifUAAAAC/hold-on.gif" />
      </template>
    </Suspense>
  </div>
</template>

<style scoped>
h1 {
  color: green;
  font-size: 35px;
}
</style>
