<template>
  <div class="">
    <h1>hello from contant</h1>
    <div class="carts" v-for="x in carts" :key="x">
      <cart title="something" :body="body[x]" />
      <img src="../assets/svgs/nodejs.svg" alt="" />
    </div>
  </div>
</template>

<script setup>
let carts = ref([0, 1]);
async function load_data() {
  // let { data: something } = await useFetch("https");
}
let body = ref([
  ["one", "two"],
  ["three", "four"],
]);
</script>

<style></style>
