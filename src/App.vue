<script setup>
import { ref } from "vue";

let tasks = ref([]);

const addTaskForm = ref({
  title: "",
  description: "",
});
const addTask = () => {
  tasks.value.push(addTaskForm.value);
};
</script>

<template>
  <header>Todo Application</header>
  <main>
    <form @submit.prevent="addTask">
      <input
        type="text"
        v-model="addTaskForm.title"
        placeholder="Enter title"
      />
      <textarea
        v-model="addTaskForm.description"
        cols="30"
        rows="10"
        placeholder="Enter description"
      >
      </textarea>
      <button type="submit">Save</button>
    </form>
    {{ tasks }}
  </main>
</template>

<style lang="scss" scoped>
form {
  max-width: 400px;
  width: 100%;
  display: flex;
  flex-direction: column;
  gap: 1rem;
  padding: 1rem;
}
</style>
