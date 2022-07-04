<template>
  <div class="bg-white text-xl text-black text-center rounded-lg border-4">
    <div
      class="bg-gradient-to-r from-blue-500 to-purple-600 rounded-lg text-left text-white p-4 flex"
    >
      <p class="text-left flex-auto">Todo List App for newbie</p>
      <a-button
        class="float-right bg-gradient-to-r from-green-500 to-blue-600 flex-auto rounded-full py-2"
        type="primary"
        @click="showModal"
      >
        Add new Task
      </a-button>
      <a-modal v-model:visible="visible" title="Basic Modal" @ok="handleOk">
        <p>Some contents...</p>
      </a-modal>
    </div>

    <div class="flex pt-3 p-2">
      <p class="flex-1">ID</p>
      <p class="flex-1">Task Name</p>
      <p class="flex-1">Status</p>
      <p class="flex-1">Edit</p>
      <p class="flex-1">Delete</p>
    </div>

    <todo-task :name="todo" />
  </div>
</template>

<script setup lang="ts">
import TodoTask from "../components/TodoTask.vue";
import { defineComponent, ref } from "vue";

const todo = ref({ id: "1", name: "task1", status: "Processing" });
const visible = ref<boolean>(false);

const showModal = () => {
  visible.value = true;
};

const handleOk = (e: any) => {
  console.log(e);
  visible.value = false;
};
</script>

<style></style>
