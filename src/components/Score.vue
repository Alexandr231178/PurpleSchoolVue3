<script setup>
    import StatisticIcon from '../icons/StatisticIcon.vue';
    
    const {stata} = defineProps({
        stata: Number,
    })
</script>

<template>
    <div class="statistic">
        <h3 class="statistic-content">{{ stata }}</h3>
        <StatisticIcon />
    </div>
</template>

<style scoped>
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