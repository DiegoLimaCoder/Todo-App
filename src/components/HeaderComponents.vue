<script setup lang="ts">
import { ref } from 'vue'

// Criando uma referência reativa para o input
const inputs = ref('')

// Função para lidar com o envio do formulário
const onSubmit = () => {
  console.log(inputs.value)
  // Emitindo o evento 'add-task' com o valor do input
  emit('add-task', inputs.value)
  inputs.value = ''
}

// Usando o helper defineEmits para definir os eventos emitidos pelo componente
const emit = defineEmits(['add-task'])
</script>

<template>
  <h1>Todo App</h1>
  <form @submit.prevent="onSubmit">
    <input type="text" placeholder="Add your new todo" class="input" v-model="inputs" />
    <button class="addbuton">+</button>
  </form>
</template>

<style scoped>
h1 {
  margin-bottom: 20px;
}

form {
  display: flex;
  align-items: center;
}

.input {
  width: 300px;
  height: 46px;
  padding: 15px;
  font-size: 16px;
  margin-right: 8px;
}

.addbuton {
  height: 48px;
  width: 48px;
  font-size: 40px;
  color: #fff;
  background-color: #8e4be8;
  line-height: 48px;
  border: none;
  border-radius: 4px;
  cursor: pointer;
}
</style>
