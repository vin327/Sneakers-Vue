<template>
  <div class="flex items-center border border-slate-200 p-4 rounded-xl gap-4">
    <img class="w-16 h-16" :src="imageUrl" alt="Sneaker" />

    <div class="flex flex-col flex-1">
      <p>{{ title }}</p>

      <div class="flex justify-between mt-2">
        <b class="flex-1"> {{ price }} </b>
        <img
          @click="emit('onClickRemove')"
          class="opacity-30 hover:opacity-100 cursor-pointer transition"
          src="/close.svg"
          alt=""
        />
      </div>
    </div>
  </div>
</template>

<script setup>
import { defineEmits } from 'vue';
const emit = defineEmits(["onClickRemove"]);

defineProps({
  id: Number,
  imageUrl: String,
  title: String,
  price: Number,
});
</script>

<style lang="scss" scoped></style>
