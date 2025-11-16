<template>
  <div class="bg-gray-100 min-h-screen font-sans antialiased">
    
    <header class="bg-white border-b border-gray-200">
      <div class="max-w-3xl mx-auto py-4 px-5">
        <h1 class="text-xl font-semibold text-gray-700">PHP Workshop To-Do</h1>
      </div>
    </header>

    <main class="max-w-3xl mx-auto p-5">

      <div v-if="error" class="mt-4 p-3 bg-red-100 text-red-700 rounded-md">
        <strong>Erro:</strong> {{ error }}
        <p class="text-sm">Verifique se sua API PHP está rodando em: <strong>{{ apiUrl }}</strong></p>
      </div>
      
      <div v-if="isLoading" class="mt-4 text-center text-gray-500">
        Carregando...
      </div>

      <AddTaskForm @submit="handleAddTask" class="mt-4" />

      <div class="bg-white rounded-lg shadow-sm mt-5">
        <ul v-if="tasks.length > 0" class="divide-y divide-gray-200">
          <TaskItem 
            v-for="task in tasks" 
            :key="task.id" 
            :task="task"
            @update="handleUpdateTask"
            @delete="handleDeleteTask"
          />
        </ul>
        <div v-else-if="!isLoading" class="p-6 text-center text-gray-500">
          Nenhuma tarefa encontrada. Adicione uma!
        </div>
      </div>

    </main>
  </div>
</template>

<script setup>
import AddTaskForm from '~/components/AddTaskForm.vue';
import TaskItem from '~/components/TaskItem.vue';

// --- Estado Reativo ---
// 1. Pega a configuração de runtime
const config = useRuntimeConfig();
// 2. A URL da API agora é uma constante lida do .env
const apiUrl = config.public.apiUrl; 

const tasks = ref([]);
const isLoading = ref(false);
const error = ref(null);

// --- Funções da API ---
async function fetchTasks() {
  if (!apiUrl) return; 
  
  isLoading.value = true;
  error.value = null;
  
  try {
    const data = await $fetch(apiUrl, { /* ... */ });
    tasks.value = data; 
  } catch (e) {
    console.error(e);
    error.value = `Falha ao conectar à API: ${e.message}`;
  } finally {
    isLoading.value = false;
  }
}

async function handleAddTask(title) {
  // ... (a lógica interna do handleAddTask continua a mesma)
  // ...
  try {
    const newTask = { title: title, status: 'Pendente' };
    await $fetch(apiUrl, {
      method: 'POST',
      body: newTask
    });
    await fetchTasks(); 
  } catch (e) {
    // ...
  }
}

// ... (handleUpdateTask, handleDeleteTask) ...

// 3. Busca as tarefas assim que o componente for "montado" (carregado)
onMounted(() => {
  fetchTasks();
});
</script>