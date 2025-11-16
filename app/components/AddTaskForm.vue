<template>
  <form @submit.prevent="submitTask" class="bg-white rounded-lg shadow-sm p-2 flex items-center">
    <Icon name="ph:plus-bold" class="h-6 w-6 text-google-blue mx-3" />
    <input
      v-model="title"
      type="text"
      placeholder="Adicionar uma tarefa..."
      class="flex-1 p-2 border-none ring-0 focus:ring-0 text-gray-900 placeholder-gray-500 text-sm"
    />
    <button
      type="submit"
      :disabled="!title"
      class="px-4 py-2 text-sm font-medium rounded-md text-white bg-google-blue hover:bg-blue-600 disabled:bg-gray-300"
    >
      Salvar
    </button>
  </form>
</template>

<script setup>
const title = ref('');
const emit = defineEmits(['submit']);

function submitTask() {
  if (title.value.trim()) {
    emit('submit', title.value.trim());
    title.value = ''; // Limpa o input
  }
}
</script>