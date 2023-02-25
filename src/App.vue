<script setup>
import { ref } from "vue";
import Card from "./components/Card.vue";

const dataSurah = ref([]);

const API = `https://al-quran-8d642.firebaseio.com/surat/56.json?print=pretty`;

const fetchApi = async () => {
  const res = await fetch(API);
  const data = await res.json();

  dataSurah.value = data;

  return data;
};

fetchApi();
</script>

<template>
  <h1 className="text-3xl font-bold text-emerald-600 font-slab text-center py-5 border border-b-2 border-x-0 border-emerald-400">Surah Al Waqiah</h1>

  <div class="flex flex-col gap-y-2 max-w-3xl py-6 mx-auto divide-y-4 divide-green-100">
    <Card v-for="data in dataSurah" :data="data" :key="data.nomor" />
  </div>
</template>
