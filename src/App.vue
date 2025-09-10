<script setup>
  import { ref } from "vue";

  import Button from "./components/Button.vue"
  import Header from "./components/Header.vue";
  // import CardContainer from "./components/CardContainer.vue";
  import Card from "./components/Card.vue";



  const cardData = ref({
    cardNumber: "03",
    word: "Auto",
    translation: "Автомобиль",
    state: "closed" | "opened",
    status: "success" | "fail" | "pending",
  })
  function cardTurnNow(turnCard) {
    pass
  }
</script>

<template>
  <main class="main">
    <Header />
    <Card v-bind="cardData" @clickTurn="cardTurnNow"/>
    <!-- <CardContainer v-bind="cardData"/> -->
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
