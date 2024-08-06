<script setup lang="ts">
import { defineProps, defineEmits } from 'vue'

// Definindo as props
const props = defineProps({
  tasks: {
    type: Array,
    required: true
  }
})

// Definindo os eventos emitidos pelo componente
const emit = defineEmits(['remove-task'])

// Função para remover a tarefa
const removeTask = (index: number) => {
  emit('remove-task', index)
}
</script>

<template>
  <div class="listTask">
    <ul class="list">
      <li v-for="(task, index) in tasks" :key="index">
        {{ task }}
        <button>
          <i class="pi pi-trash trash-icons" @click="removeTask(index)"></i>
        </button>
      </li>
    </ul>
  </div>
</template>

<style scoped>
.list li {
  list-style: none;
  margin: 18px 0px;
  padding: 18px 0px;
  padding-left: 18px;
  height: 50px;
  display: flex;
  justify-content: space-between;
  align-items: center;
  width: auto;
  border-radius: 4px;
  background-color: #f3f1f4;
}

button {
  cursor: pointer;
  height: 50px;
  width: 60px;
  border-radius: 4px;
  border: none;
  transition: all 0.3s;
}

button:hover {
  background-color: #e64d3f;
  color: #fff;
}

.trash-icons {
  font-size: 18px;
  color: #f3f1f4;
}
</style>
