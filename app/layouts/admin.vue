<template>
  <div class="min-h-screen flex bg-slate-100 dark:bg-slate-900">
    <!-- Sidebar -->
    <aside class="w-64 bg-white dark:bg-slate-800 shadow-md flex flex-col">
      <div class="p-6 font-bold text-xl text-blue-600 dark:text-blue-400">Admin Panel</div>
      <nav class="flex-1 px-4 space-y-2">
        <NuxtLink
          to="/admin/dashboard"
          class="block py-2 px-3 rounded hover:bg-blue-50 dark:hover:bg-slate-700"
          >Dashboard</NuxtLink
        >
        <NuxtLink
          to="/admin/rooms"
          class="block py-2 px-3 rounded hover:bg-blue-50 dark:hover:bg-slate-700"
          >Quản lý phòng</NuxtLink
        >
        <NuxtLink
          to="/admin/users"
          class="block py-2 px-3 rounded hover:bg-blue-50 dark:hover:bg-slate-700"
          >Người dùng</NuxtLink
        >
        <NuxtLink
          to="/admin/bookings"
          class="block py-2 px-3 rounded hover:bg-blue-50 dark:hover:bg-slate-700"
          >Đặt phòng</NuxtLink
        >
      </nav>
    </aside>

    <!-- Main content -->
    <div class="flex-1 flex flex-col">
      <!-- Header -->
      <header class="bg-white dark:bg-slate-800 shadow-md p-4 flex justify-between items-center">
        <h2 class="text-lg font-semibold text-slate-900 dark:text-white">Admin Dashboard</h2>
        <Button label="Đăng xuất" />
      </header>

      <!-- Page content -->
      <main class="flex-1 p-6 overflow-auto">
        <slot />
      </main>
    </div>
  </div>
</template>

<script setup lang="ts">
import Button from '~/components/Button.vue';
</script>
