<script setup>
    import { ref } from 'vue';
    
    // const {cardNumber="01", word="Word"} = defineProps({
    //     cardNumber: String,
    //     word: String
    // })

    const cardData = ref({
    cardNumber: "03",
    word: "Auto",
    translation: "Автомобиль",
    state: "closed" | "opened",
    status: "success" | "fail" | "pending",
  })

    const emit = defineEmits(["clickTurn"])
    function turnCard() {
        emit("clickTurn", "turnCard");
    }

</script>

<template>
    <div class="card">
        <div class="card-content" @click="turnCard()">
            <div class="card-number">{{ cardData.cardNumber }}</div>
            <h4>{{ cardData.word }}</h4>
            <div class="card-turn">Перевернуть</div>
        </div>
    </div>
    
</template>

<style scoped>
    .card {
        color: #000;
        display: flex;
        justify-content: center;
        align-items: center;
        width: 250px;
        height: 376px;
        background-color: var(--color-bg-card);
        box-shadow: 10px 10px 10px 0px rgba(0, 0, 0, 0.05);
        border-radius: 16px;
        cursor: pointer;
    }


    .card-content {
        position: relative;
        display: flex;
        justify-content: center;
        align-items: center;
        width: 212px;
        height: 320px;
        border: 1px solid rgba(204, 232, 255, 1);
        border-radius: 12px;
        font-family: var(--font2);
    }

    .card-content:hover {
        border: 2px solid rgb(166, 10, 238);
    }

    .card-number {
        position:absolute;
        top: -10px;
        left: 20px;
        z-index: 1;
        width: 16px;
        height: 16px;
        font-size: 14px;
        font-weight: 400;
        background-color: var(--color-bg-card);
        text-align: center;
    }

    .card-turn {
        position:absolute;
        top: 312px;
        left: 60px;
        z-index: 1;
        width: 89px;
        height: 18px;
        font-size: 12px;
        font-weight: 700;
        line-height: 18px;
        letter-spacing: 12%;
        text-transform: uppercase;
        background-color: var(--color-bg-card);
        text-align: center;
    }
</style>