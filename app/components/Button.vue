<template>
  <button :class="buttonClass" :disabled="disabled || loading">
    <span v-if="loading" class="animate-pulse">Đang xử lý...</span>
    <span v-else>{{ label }}</span>
  </button>
</template>

<script setup lang="ts">
import { computed } from 'vue';

const props = defineProps<{
  label: string;
  type?: 'primary' | 'secondary' | 'success' | 'danger';
  outlined?: boolean;
  loading?: boolean;
  disabled?: boolean;
  full?: boolean;
}>();

const baseClass =
  'px-5 py-2.5 rounded-md font-semibold transition-all duration-200 focus:outline-none';

const typeClassMap: Record<string, string> = {
  primary: 'bg-blue-600 text-white hover:bg-blue-700',
  secondary: 'bg-slate-600 text-white hover:bg-slate-700',
  success: 'bg-green-600 text-white hover:bg-green-700',
  danger: 'bg-red-600 text-white hover:bg-red-700',
};

const outlinedClassMap: Record<string, string> = {
  primary: 'border border-blue-600 text-blue-600 hover:bg-blue-50',
  secondary: 'border border-slate-600 text-slate-600 hover:bg-slate-50',
  success: 'border border-green-600 text-green-600 hover:bg-green-50',
  danger: 'border border-red-600 text-red-600 hover:bg-red-50',
};

const buttonClass = computed(() => {
  const type = props.type ?? 'primary';

  return [
    baseClass,
    props.full ? 'w-full' : 'w-auto',
    props.disabled ? 'opacity-50 cursor-not-allowed' : 'cursor-pointer',
    props.outlined ? outlinedClassMap[type] : typeClassMap[type],
  ];
});
</script>
