<template>
  <div class="flex text-center p-4 m-2">
    <p class="flex-1">{{ name.id }}</p>
    <p class="flex-1 text-black">{{ name.name }}</p>
    <p class="flex-1">{{ name.status }}</p>
    <button class="flex-1 bg-yellow-500 text-center text-black rounded-md">
      Edit
    </button>
    
    <button class="flex-1 bg-red-500 text-center text-black rounded-md">
      Delete
    </button>
  </div>
</template>

<script setup>
defineProps({
  name: {
    type: Object,
  },
});
</script>

<style></style>
