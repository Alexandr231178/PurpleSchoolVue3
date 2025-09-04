<script setup>
  import Button from "./components/Button.vue"
  const date = new Date();
</script>

<template>
  <h1>{{ date.toLocaleDateString() }}</h1>
  <Button>Сохранить</Button>
</template>

<style scoped>

</style>
