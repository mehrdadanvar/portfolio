<template>
  <div class="">
    <div class="">
      <img src="../assets/svgs/education.svg" alt="" width="50" />
      <h1 class="text-2xl">Education</h1>
    </div>
    <div id="wrapper">
      <div v-for="x in schools" :key="x" class="my-6">
        <div class="flex felx-row">
          <div class="objec-cover bg-slate-200 rounded-l-lg py-4 px-4">
            <img class="" src="../assets/svgs/school1.svg" alt="" width="100" />
          </div>
          <div
            class="border-2 border-slate-200 rounded-r-lg py-4 px-6 w-3/5 h-52"
          >
            <div class="flex flex-row gap-6 font-bold">
              <h4>{{ x.name }}</h4>
              <p>{{ x.dates }}</p>
            </div>
            <p>{{ x.major }}</p>
            <p>{{ x.level }}</p>
            <p>{{ x.location }}</p>
            <span>GPA {{ x.grade }}</span>
            <p>{{ x.remarks }}</p>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script setup>
let { data: schools } = await useFetch("/api/schools");
console.log(schools);

let school_logos = ref([
  "../assets/svgs/school1.svg",
  "../assets/svgs/school2.png",
]);
</script>

<style></style>
