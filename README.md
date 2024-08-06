# Todo App

Este é um aplicativo simples de lista de tarefas (Todo App) construído com Vue 3 e TypeScript. Ele permite adicionar, remover e limpar tarefas.

## Estrutura do Projeto

### App.vue

O componente principal que gerencia o estado da aplicação, incluindo a lista de tarefas. Ele contém:

- **Estado Reativo:** Armazena a lista de tarefas.
- **Funções:**
  - `addTask(task: string)`: Adiciona uma nova tarefa à lista.
  - `removeTask(index: number)`: Remove uma tarefa da lista pelo índice.
  - `clearTasks()`: Limpa toda a lista de tarefas.
- **Template:**
  - Inclui `HeaderComponentsVue` para capturar a entrada do usuário.
  - Inclui `ListComponentsVue` para exibir e remover tarefas.
  - Botão para limpar todas as tarefas.

### HeaderComponents.vue

Componente que captura a entrada do usuário para adicionar uma nova tarefa. Ele contém:

- **Referência Reativa:** Armazena o valor do input do usuário.
- **Função:**
  - `onSubmit()`: Emite o evento `add-task` com o valor do input e limpa o input.
- **Template:**
  - Formulário com input ligado à referência reativa via `v-model`.
  - Botão para enviar a nova tarefa.

### ListComponents.vue

Componente que exibe a lista de tarefas e permite remover tarefas. Ele contém:

- **Props:** Recebe a lista de tarefas do componente pai (`App.vue`).
- **Função:**
  - `removeTask(index: number)`: Emite o evento `remove-task` com o índice da tarefa a ser removida.
- **Template:**
  - Renderiza a lista de tarefas com `v-for`.
  - Botão para remover cada tarefa.

## Como Executar o Projeto

### Pré-requisitos

- Node.js instalado
- Gerenciador de pacotes npm ou yarn

### Passos para Execução

1. **Clone o repositório:**

   ```bash
   git clone https://github.com/seu-usuario/todo-app.git
   ```

2. **Navegue até o diretório do projeto:**

   ```bash
   cd todo-app
   ```

3. **Instale as dependências:**

   ```bash
   npm install
   # ou
   yarn install
   ```

4. **Execute o servidor de desenvolvimento:**

   ```bash
   npm run dev
   # ou
   yarn dev
   ```

5. **Abra o navegador e acesse:**

   ```
   http://localhost:3000
   ```

## Estrutura de Arquivos

```
todo-app/
├── public/
│   ├── index.html
├── src/
│   ├── assets/
│   ├── components/
│   │   ├── HeaderComponents.vue
│   │   ├── ListComponents.vue
│   ├── App.vue
│   ├── main.ts
├── package.json
├── tsconfig.json
├── vite.config.ts
```

## Funcionalidades

- **Adicionar Tarefa:** Adicione uma nova tarefa usando o input na parte superior.
- **Remover Tarefa:** Remova uma tarefa específica clicando no ícone de lixeira ao lado dela.
- **Limpar Todas as Tarefas:** Limpe toda a lista de tarefas usando o botão "Clear All Tasks".

## Tecnologias Utilizadas

- **Vue 3:** Framework JavaScript para construção de interfaces de usuário.
- **TypeScript:** Superconjunto do JavaScript que adiciona tipagem estática ao código.
- **Vite:** Ferramenta de build rápida e leve para projetos Vue.js.

## Contribuição

Contribuições são bem-vindas! Sinta-se à vontade para abrir uma issue ou enviar um pull request.

## Licença

Este projeto está licenciado sob a licença MIT. Veja o arquivo [LICENSE](LICENSE) para mais detalhes.

---


