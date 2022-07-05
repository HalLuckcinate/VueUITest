<template>
  <div class="flex text-center p-4 m-2 text-black">
    <p class="flex-1">{{ id }}</p>
    <p class="flex-1">{{ name }}</p>
    <p class="flex-1">{{ status }}</p>
    <button
      @click="$emit('edit', id)"
      class="flex-1 !bg-yellow-500 text-center text-black rounded-md m-0.5"
    >
      Edit
    </button>

    <button
      @click="$emit('delete')"
      class="flex-1 bg-red-500 text-center text-black rounded-md m-0.5"
    >
      Delete
    </button>
  </div>
</template>

<script setup>
defineProps({
  id: {
    type: String,
  },
  name: {
    type: String,
  },
  status: {
    type: String,
  },

  showModaltask: {
    type: Function,
  },
});

defineEmits(["delete", "edit"]);
</script>

<style></style>
