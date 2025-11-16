<template>
  <div class="p-4 bg-white rounded-lg shadow-sm border border-google-blue/50">
    <label for="api-url" class="block text-sm font-medium text-gray-700">
      <Icon name="ph:plugs-bold" class="mr-1" />
      URL da sua API PHP
    </label>
    <div class="mt-2 flex gap-2">
      <input
        type="text"
        id="api-url"
        :value="url"
        @input="$emit('update:url', $event.target.value)"
        placeholder="https://...php.new/p/..."
        class="flex-1 block w-full rounded-md border-gray-300 shadow-sm focus:border-google-blue focus:ring-google-blue sm:text-sm"
      />
      <button
        @click="$emit('refresh')"
        title="Atualizar Lista"
        class="inline-flex items-center px-4 py-2 border border-transparent text-sm font-medium rounded-md shadow-sm text-white bg-google-blue hover:bg-blue-600 focus:outline-none focus:ring-2 focus:ring-offset-2 focus:ring-google-blue"
      >
        <Icon name="ph:arrow-clockwise-bold" class="h-5 w-5" />
      </button>
    </div>
  </div>
</template>

<script setup>
// Define o v-model e o evento
defineProps(['url']);
defineEmits(['update:url', 'refresh']);
</script>