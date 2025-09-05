<script setap>
</script>

<template>
    <button class="button"><slot></slot></button>
</template>

<style scoped>
    .button {
        width: 315px;
        border: none;
        border-radius: 100px;
        background: var(--color-bg-btn2);
        padding: 16px 8px;
        font-family: var(--font2);
        font-size: 24px;
        line-height: 36px;
        font-weight: 400;
        color: var(--primary);
        cursor: pointer; 
    }

    .button:hover {
        background: var(--color-bg-btn2-hover);
    }
</style>