<script setup>
  import { ref } from 'vue';
  import Button from "./components/Button.vue"
  import Header from "./components/Header.vue";
  // import CardContainer from "./components/CardContainer.vue";
  import Card from "./components/Card.vue";

  const statistica = ref(25);

  const cardData = ref({
    cardNumber: "03",
    word: "Auto",
    translation: "Автомобиль",
    state: "closed",
    status: "success",
  })

  function cardTurnNow(turnCard) {}

</script>

<template>
  <main class="main">
    <Header v-bind="statistica" />
    <Card v-bind="cardData" @clickTurn="cardTurnNow"/>
    <Button class="restart-button">Начать заново</Button>
  </main>
  
</template>

<style scoped>
  .main {
    background: var(--colog-bg2);
    padding: 60px 50px;
    border-radius: 25px;
    text-align: center;
  }

  .restart-button {
    margin: 0 auto;
  }

</style>
