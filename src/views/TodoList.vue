<template>
  <div class="bg-white text-xl text-black text-center rounded-lg border-4">
    <div
      class="bg-gradient-to-r from-blue-500 to-purple-600 rounded-lg text-left text-white p-4 flex"
    >
      <p class="text-left flex-auto text-2xl font-bold">
        Todo List App for newbie
      </p>
      <button class="btn-add" type="primary" @click="showModal">
        Add New Task
      </button>
      <a-modal
        v-model:visible="visible"
        title="Insert tasks information"
        @ok="handleOk"
        class=""
      >
        <div class="text-xl font-bold">ID</div>
        <a-input class="input" v-model:value="idTodo" />

        <div class="text-xl font-bold">Task Name</div>
        <a-input class="input" v-model:value="nameTodo" id="new-nameTodo" />

        <div class="text-xl font-bold">Status</div>
        <a-input class="input" v-model:value="statusTodo" id="new-statusTodo" />
      </a-modal>

      <a-modal
        v-model:visible="visibleModalEdit"
        title="Edit tasks information"
        @ok="editOk"
        class=""
      >
        <div class="text-xl font-bold">ID</div>
        <a-input class="input" v-model:value="idTodoedit" />

        <div class="text-xl font-bold">Task Name</div>
        <a-input class="input" v-model:value="nameTodoedit" id="new-nameTodo" />

        <div class="text-xl font-bold">Status</div>
        <a-input
          class="input"
          v-model:value="statusTodoedit"
          id="new-statusTodo"
        />
      </a-modal>
    </div>

    <div class="flex pt-3 p-2">
      <p class="flex-1">ID</p>
      <p class="flex-1">Task Name</p>
      <p class="flex-1">Status</p>
      <p class="flex-1">Edit</p>
      <p class="flex-1">Delete</p>
    </div>

    <todo-task
      v-for="(todo, index) in todos"
      :key="todo.id"
      :id="todo.id"
      :name="todo.name"
      :status="todo.status"
      @edit="(id: string) => showEdit(id)"
      @delete="todos.splice(index, 1)"
    />
  </div>
</template>

<script setup lang="ts">
import TodoTask from "../components/TodoTask.vue";
import { defineComponent, ref } from "vue";

const todos = ref([
  { id: "1", name: "task1", status: "Processing" },
  { id: "2", name: "task2", status: "Processing" },
  { id: "3", name: "task3", status: "Todo" },
  { id: "4", name: "task4", status: "Done" },
]);

const visible = ref<boolean>(false);
const visibleModalEdit = ref<boolean>(false);
const idToEdit = ref<string>("");

const showModal = () => {
  visible.value = true;

  idTodo.value = "";
  nameTodo.value = "";
  statusTodo.value = "";
};

const showEdit = (id: string) => {
  idToEdit.value = id;
  visibleModalEdit.value = true;
};

const editOk = (e: any) => {
  console.log(e);
  visibleModalEdit.value = false;

  editTask();
};

const handleOk = (e: any) => {
  console.log(e);
  visible.value = false;
  visibleModalEdit.value = false;

  addNew();
};

const nameTodo = ref("");
const statusTodo = ref("");
const idTodo = ref("");

const nameTodoedit = ref("");
const statusTodoedit = ref("");
const idTodoedit = ref("");

function addNew() {
  todos.value.push({
    id: idTodo.value,
    name: nameTodo.value,
    status: statusTodo.value,
  });
}

function editTask() {
  for (let i = 0; i < todos.value.length; i++) {
    const element = todos.value[i];

    if (element.id === idToEdit.value) {
      element.id = idTodoedit.value;
      element.name = nameTodoedit.value;
      element.status = statusTodoedit.value;
    }
  }
  // todos.value.push({
  //   id: idTodoedit.value,
  //   name: nameTodoedit.value,
  //   status: statusTodoedit.value,
  // });
}
</script>

<style>
.btn-add {
  background-image: linear-gradient(
    to right,
    rgb(44, 44, 243),
    rgb(72, 199, 151)
  );
  font-size: 18px;
  font-weight: 400;
  border-radius: 10px;
  font-weight: bold;
  padding: 5px;
}

.input {
  background-color: #f4f4f4;
  font-size: 20px;
  border: 3px solid;
  border-top-color: blue;
  border-left-color: blue;
  border-bottom-color: blueviolet;
  border-right-color: blueviolet;
  padding-block: 5px;
}
</style>
vbas
