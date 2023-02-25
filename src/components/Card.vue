<script setup>
import { defineProps } from "vue";

const { data } = defineProps(["data"]);
</script>

<template>
  <div class="flex flex-col gap-y-2 px-4 py-3">
    <p class="p-1 bg-green-300 w-8 text-center">{{ data.nomor }}.</p>

    <div class="flex justify-end text-lg">
      <p>
        {{ data.ar }}
      </p>
    </div>

    <p class="font-slab">{{ data.id }}</p>
  </div>
</template>
