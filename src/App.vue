<script setup>
  const date = new Date();
</script>

<template>
  <h1>{{ date.toLocaleDateString() }}</h1>
  
</template>

<style scoped></style>
