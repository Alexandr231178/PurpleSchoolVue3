<script setup>
  import { ref } from 'vue';
  import Button from "./components/Button.vue"
  import Header from "./components/Header.vue";
  import CardContainer from "./components/CardContainer.vue";
  

  const statistica = ref(0);

  const cardDataList = ref([
    {
    cardNumber: "01",
    word: "Auto",
    translation: "Автомобиль",
    state: "closed",
    status: "success",
  },
  {
    cardNumber: "02",
    word: "Table",
    translation: "Стол",
    state: "closed",
    status: "success",
  },
  {
    cardNumber: "03",
    word: "Apple",
    translation: "Яблоко, а не телефон",
    state: "closed",
    status: "success",
  }
  ]
    
)

  function cardTurnNow(turnCard) {}

</script>

<template>
  <main class="main">
    <Header :stata="statistica" />
    <CardContainer v-bind="cardDataList"/>
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

  p {
      color: black;
  }

</style>
