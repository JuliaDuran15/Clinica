<script setup>

</script>
<template>
    <div class="max-w-7xl mx-auto">
      <div v-if="authStore.user">
        <h1>{{ authStore.user.name }}</h1>
        <p>{{ authStore.user.email }}</p>
      </div>
      <div v-else>
        <h1>Go and login</h1>
      </div>
    </div>
  </template>