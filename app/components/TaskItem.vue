<template>
  <li class="flex items-center p-3 hover:bg-gray-50">
    
    <button @click="toggleComplete" class="mr-3 flex-shrink-0">
      <Icon 
        :name="isCompleted ? 'ph:check-circle-fill' : 'ph:circle-thin'"
        class="h-6 w-6"
        :class="isCompleted ? 'text-google-blue' : 'text-gray-500'"
      />
    </button>
    
    <div class="flex-1" @click="toggleComplete">
      <p class="text-sm font-medium text-gray-900" :class="{ 'line-through text-gray-500': isCompleted }">
        {{ task.title }}
      </p>
      <p v-if="task.description" class="text-xs text-gray-500" :class="{ 'line-through': isCompleted }">
        {{ task.description }}
      </p>
      <div v-if="task.dueDate" class="text-xs text-blue-600 mt-1 flex items-center gap-1">
        <Icon name="ph:calendar-blank-thin" />
        <span>{{ new Date(task.dueDate).toLocaleDateString() }}</span>
      </div>
    </div>
    
    <button @click="toggleStar" class="ml-3 p-2 text-gray-400 hover:text-yellow-500 flex-shrink-0">
      <Icon 
        :name="task.starred ? 'ph:star-fill' : 'ph:star-thin'"
        class="h-5 w-5"
        :class="{ 'text-yellow-400': task.starred }"
      />
    </button>

    <button @click="$emit('delete', task.id)" class="ml-2 p-2 text-gray-400 hover:text-red-500 flex-shrink-0">
        <Icon name="ph:trash-thin" class="h-5 w-5" />
    </button>
  </li>
</template>

<script setup>
const props = defineProps({
  task: {
    type: Object,
    required: true
  }
});

const emit = defineEmits(['update', 'delete']);

// O modelo de dados do Google Tasks é complexo.
// Vamos nos concentrar em 'title' e 'status'.
const isCompleted = computed(() => props.task.status === 'Concluída');

// Emite um evento de 'update' quando o status muda
function toggleComplete() {
  const newStatus = isCompleted.value ? 'Pendente' : 'Concluída';
  emit('update', { ...props.task, status: newStatus });
}

function toggleStar() {
  emit('update', { ...props.task, starred: !props.task.starred });
}

</script>