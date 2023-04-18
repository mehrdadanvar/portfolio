<template>
  <div class="font-normal">
    <img src="../assets/svgs/publication.svg" alt="" width="70" />
    <h4 class="text-2xl mb-4">Peer Reviewed Publications</h4>
    <div class="grid grid-cols-2">
      <div class="mb-12 px-1 flex flex-col" v-for="pub in pubs" :key="pub">
        <div class="bg-slate-200 rounded-t-lg py-4 px-4">
          <img
            src="../assets/svgs/cjt1.jpg"
            alt=""
            width="100"
            class="rounded-full reletaive mx-auto -mt-12"
          />
        </div>
        <div class="border-2 border-slate-200 rounded-b-lg py-4 px-6">
          <h4 class="font-bold mb-3">{{ pub.title }}</h4>
          <div class="flex flex-row w-80 justify-items-end my-2">
            <p class="italic text-slate-500">{{ pub.journal }}.</p>
            <p class="text-slate-500">{{ pub.year }}</p>
          </div>
          <div class="my-2">
            <span
              class="mr-1 text-slate-500"
              v-for="(author,index) in pub.authors"
              :key="index"
              >{{ author }}{{ index < pub.authors.length -1 ? ", " : "."  }}</span
            >
          </div>
          <div class="flex flex-row my-2 justify-between">
            <a :href="pub.pdf">PDF</a>
          </div>
          <!-- <p class="bg-red-300">{{ pub.id }}</p> -->
          <!-- <p v-show="isOpen">{{ pub.abstract }}</p> -->
          <div class="">
            <button class="border-0" @click="isOpen = true">
              view abstract
            </button>
            <teleport to="body">
              <div
                class="absolute mt-96 bg-blue-900 text-white px-12 py-12 mx-96 border rounded-2xl leading-7"
                v-if="isOpen"
              >
                <div class="modal-content">
                  <p>{{ pub.abstract }}</p>
                  <button @click="isOpen = false" class="bg-white text-black">
                    close abstract
                  </button>
                </div>
              </div>
            </teleport>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script setup>
let { data: pubs } = await useFetch("/api/pubs");
console.log(pubs.value);
let isOpen = ref(false);
</script>

<style scoped>

</style>
