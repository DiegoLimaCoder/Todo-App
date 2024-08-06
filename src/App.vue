<script setup lang="ts">
import { ref } from 'vue'
import HeaderComponents from './components/HeaderComponents.vue'
import ListComponents from './components/ListComponents.vue'

// Estado das tarefas no componente pai
const tasks = ref<string[]>([])

// Função para adicionar uma nova tarefa
function addTask(task: string) {
  if (task.trim() !== '') {
    tasks.value.push(task)
  }
}

const removeTask = (index: number) => {
  tasks.value.splice(index, 1)
}

const clearTasks = () => {
  tasks.value = []
}
</script>

<template>
  <div class="container">
    <div class="card">
      <HeaderComponents @add-task="addTask" />
      <ListComponents :tasks="tasks" @remove-task="removeTask" />

      <div class="btnClearAll">
        <button @click="clearTasks">Clear all</button>
      </div>
    </div>
  </div>
</template>

<style scoped>
.card {
  display: grid;
  width: 424px;
  height: auto;
  padding: 38px;
  background-color: #fff;
  border-radius: 8px;
}

.btnClearAll {
  justify-self: flex-end;
  margin-top: 30px;
}

.btnClearAll button {
  height: 40px;
  width: 80px;
  border: none;
  border-radius: 8px;
  color: #fff;
  background-color: red;
  font-size: 18px;
  cursor: pointer;
}
</style>
