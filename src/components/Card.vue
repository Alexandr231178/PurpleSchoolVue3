<script setup>
    import Tickk2 from '../icons/Tickk2.vue';
    import Tick from '../icons/Tick.vue';
    import CloseSquare from '../icons/CloseSquare.vue';
    import CloseSquare2 from '../icons/CloseSquare2.vue';

    const cardData = defineProps({
        cardNumber: String,
        word: String,
        translation: String,
        state: String,
        status: String,
    })


    const emit = defineEmits(["clickTurn"])
    function turnCard() {
        emit("clickTurn", "cardData.cardNumber");
    }

</script>

<template>
    <div class="card">
        <div v-if="cardData.state === 'closed'" class="card-content">
            <div class="card-number">{{ cardData.cardNumber }}</div>
            <h4>{{ cardData.word }}</h4>
            <div v-if="cardData.status ==='success'" class="card-turn" @click="turnCard()">Перевернуть</div>
        </div>

        <div v-if="cardData.state === 'opened'" class="card-content">
            <div class="card-number">{{ cardData.cardNumber }}</div>
            <h4>{{ cardData.translation }}</h4>

            <div v-if="cardData.status ==='success'" class="card-turn">
                <div class="close-tick-container">
                    <CloseSquare />
                    <Tick />
                </div>
            </div>
            <div v-else class="card-turn">Завершено</div>

            <div v-if="cardData.status ==='fail'" class="result-icon"><CloseSquare2 /></div>
            <div v-if="cardData.status ==='pending'" class="result-icon"><Tickk2 /></div>
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
        cursor: pointer;
    }

    .close-tick-container {
        display: flex;
        width: 80px;
        justify-content: space-between;
    }

    .result-icon {
        position: absolute;
        top: -25px;
        left: 90px;
        z-index: 1;

    }
</style>