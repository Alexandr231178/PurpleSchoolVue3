<script setup>
  import { onMounted, ref } from 'vue';
  import Button from "./components/Button.vue"
  import Header from "./components/Header.vue";
  import Card from "./components/Card.vue";
  
  const API_ENDPOINT = 'http://localhost:8080/api/random-words';

  let statistica = ref(0);

  function turnCard(cardNumber) {
    cardDataList.value[cardNumber-1].state = 'opened';
    // console.log(`Нажата карточка номер ${cardNumber}, статус карточки ${cardDataList.value[cardNumber-1].state}`);
  }

  function changeStatusFail(cardNumber) {
    cardDataList.value[cardNumber-1].status = 'fail';
    console.log(`Нажата карточка номер ${cardNumber}, статус карточки ${cardDataList.value[cardNumber-1].status}`);
  }

  function changeStatusPending(cardNumber) {
    cardDataList.value[cardNumber-1].status = 'pending';
    console.log(`Нажата карточка номер ${cardNumber}, статус карточки ${cardDataList.value[cardNumber-1].status}`);
    statistica.value += 1;
  }

  function restart() {
    //dataForCard(API_ENDPOINT);
    location.reload()
  }


  let cardDataList = ref([]);

  async function dataForCard(params) {
    await fetch(params).then(resp=>resp.json()).then(data=>{cardDataList.value = data});
    cardDataList.value.forEach((element, index) => {
      element.state = "closed";
      element.status = "success";
      element.cardNumber = index + 1;
    })
  }

  // onMounted(()=> {
  //   dataForCard(API_ENDPOINT);
  // })

  dataForCard(API_ENDPOINT);
</script>

<template>
  <main class="main">
    <Header :stata="statistica" />
    <div class="card-container">
      <Card v-for="card in cardDataList" :key="card.word" v-bind="card" @click-turn="turnCard" @fail="changeStatusFail" @pending="changeStatusPending"/>
    </div>
    <Button class="restart-button" @click="restart()">Начать заново</Button>
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
    width: 1300px;
    display:grid;
    grid-template-columns: 1fr 1fr 1fr 1fr 1fr;
    gap: 15px;
    margin: 0 auto;
    margin-bottom: 30px;
  }

  .restart-button {
    margin: 0 auto;
  }

  p {
      color: black;
  }

</style>
