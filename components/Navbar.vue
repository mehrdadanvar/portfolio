<template>
  <nav class="bg-slate-500">
    <div class="flex flex-row gap-6 list-none">
      <div class="list-item">
        <NuxtLink class="text" to="/">Home</NuxtLink>
      </div>
      <div class="list-item">
        <NuxtLink class="text" to="/about">About</NuxtLink>
      </div>
      <div class="list-item">
        <NuxtLink class="text" to="/contact">Contact</NuxtLink>
      </div>
      <div class="list-item">
        <NuxtLink class="text" to="/test">test</NuxtLink>
      </div>
      <div class="list-item">
        <NuxtLink class="text" to="/mehrdad">mehrdad</NuxtLink>
      </div>
      <div class="list-item">
        <NuxtLink class="text" to="/headless">headless</NuxtLink>
      </div>
    </div>
  </nav>
</template>

<script>
export default {
  name: "Navbar",
};
</script>

<style scoped></style>
