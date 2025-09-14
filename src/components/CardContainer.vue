<script setup>
    import Card from './Card.vue';

    const cardData = defineProps()
    //     cardNumber: String,
    //     word: String,
    //     translation: String,
    //     state: String,
    //     status: String,
    // },
    // {
    //         cardNumber: String,
    //         word: String,
    //         translation: String,
    //         state: String,
    //         status: String,
    //     },
    // {
    //         cardNumber: String,
    //         word: String,
    //         translation: String,
    //         state: String,
    //         status: String,
    //     })


    const emit = defineEmits(["clickTurn"])
    function turnCard() {
        emit("clickTurn", "turnCard");
    }


</script>

<template>
    <div class="card-container">
        <!-- <Card /> -->
        <p>{{ cardData }}</p>

    </div>
</template>

<style scoped>
    .card-container {
        width: 1440px;
        margin: 0 auto;
        margin-bottom: 100px;
    }

    p {
        color: black;
    }

</style>