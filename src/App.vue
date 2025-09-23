<script setup>
  import { ref } from 'vue';
  import Button from "./components/Button.vue"
  import Header from "./components/Header.vue";
  import Card from "./components/Card.vue";
  

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
      state: "opened",
      status: "success",
    },
    {
      cardNumber: "03",
      word: "Apple",
      translation: "Яблоко, а не телефон",
      state: "opened",
      status: "fail",
    },
        {
      cardNumber: "04",
      word: "Green",
      translation: "Зеленый",
      state: "opened",
      status: "pending",
    }
    ]
      
  )

  // function turnCard(cardNumber) {
  //   console.log(`Нажата карточка номер ${cardNumber}`)
  // }

</script>

<template>
  <main class="main">
    <Header :stata="statistica" />
    <div class="card-container">
      <Card v-for="card in cardDataList" :key="card.cardNumber" v-bind="card"/>
    </div>
    
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

  .card-container {
    display:grid;
    grid-template-columns: 1fr 1fr 1fr 1fr 1fr 1fr;
    margin-bottom: 10vh;
    gap: 5px;
  }

  .restart-button {
    margin: 0 auto;
  }

  p {
      color: black;
  }

</style>
