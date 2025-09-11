<script setup>
    import Score from './Score.vue';

    const stata = defineProps({stata: Number})

</script>

<template>
    <header class="header">
        <div class="header-container">
            <h2 class="header-title">Запомни слово</h2>
            <Score v-bind="stata"/>
        </div>
    </header> 
</template>

<style scoped>
    .header {
        height: 121px;
    }

    .header-container {
        display: flex;
        width: 1440px;
        height: 100%;
        margin: 0 auto;
        justify-content: space-between;
        font-family: var(--font2);
    }

    .header-title {
        color: #000;
        text-transform: uppercase;
    }
</style>