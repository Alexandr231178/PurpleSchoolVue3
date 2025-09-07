<script setup>
    import StatisticIcon from '../icons/StatisticIcon.vue';
</script>

<template>
    <header class="header">
        <div class="header-container">
            <h2 class="header-title">Запомни слово</h2>
            <div class="statistic">
                <h3 class="statistic-content">100</h3>
                <StatisticIcon />
            </div>
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

    .statistic {
        display: flex;
        justify-content: center;
        align-items: center;
        gap: 5px;
        width: 110px;
        height: 48px;
        border-radius: 36px;
        background-color: var(--color-bg-statistic);
    }

    .statistic-content {
        color: var(--color-bg-btn2);
    }

</style>