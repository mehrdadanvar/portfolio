<template>
  <div>
    <div class="mb-12 px-1 flex flex-col h-auto min-h-full w-2/4">
      <div class="bg-purple-400 rounded-t-lg py-4 px-4">
        <img src="../assets/svgs/cjt1.jpg" alt="" width="100" class="rounded-full reletaive -mt-12 shadow-xl" />
      </div>
      <div class="border-2 border-slate-100 rounded-b-lg py-4 px-6 bg-slate-100 shadow-lg shadow-slate-400">
        <h4 class="font-bold mb-3">{{ props.title }}</h4>
        <div class="my-2 grid grid-cols-2 gap-12">
          <p class="italic text-slate-600">{{ props.journal }}.</p>
          <p class="text-slate-600">{{ props.year }}</p>
        </div>
        <div class="my-2">
          <span class="mr-1 text-slate-600" v-for="(author, index) in props.authors" :key="index">{{ author }}{{ index <
            props.authors.length - 1 ? ", " : "." }}</span>
        </div>
        <div class="flex flex-row justify-around text-sm my-6">
          <button
            class="bg-white border-2 border-slate-200 shadow-inner rounded-md w-36 h-12 hover:bg-slate-500 hover:text-white"
            @click="isOpen = !isOpen">
            {{ isOpen ? "Close" : "Read Abstract" }}
          </button>
          <button class="bg-white border-2 border-slate-200 rounded-md w-36  hover:bg-slate-500 hover:text-white">
            <a :href="props.pdf" target="_blank"> View PDF</a>

          </button>


          <!-- <p class="bg-red-300">{{ pub.id }}</p> -->
          <!-- <p v-show="isOpen">{{ pub.abstract }}</p> -->
        </div>
        <div>
          <HeadlessTransitionRoot :show="isOpen" enter="transition-opacity duration-250" enter-from="opacity-0"
            enter-to="opacity-100 text-slate-500" leave="transition-opacity duration-250" leave-from="opacity-50"
            leave-to="opacity-0">
            {{ props.abstract }}</HeadlessTransitionRoot>
        </div>

      </div>
    </div>
  </div>
</template>

<script setup>
let props = defineProps({
  title: { type: String, default: "Title" },
  journal: { type: String, default: "Journal" },
  year: { type: Number, default: "Year" },
  authors: { type: Array, default: () => ["one", "two"] },
  pdf: { type: String, default: "" },
  abstract: { type: String, default: "lorem ipsum" }
});
let isOpen = ref(false);
</script>

<style scoped></style>