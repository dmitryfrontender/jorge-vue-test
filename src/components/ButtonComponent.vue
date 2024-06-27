<template>
    <button class="button-component">
        <slot></slot>
    </button>
</template>

<script setup>

</script>

<style lang="scss" scoped>
.button-component {
    display: inline-flex;
    flex-direction: column;
    justify-content: center;
    align-self: stretch;
    padding: 0px 58px;
    align-items: flex-start;
    gap: 10px;
    border-radius: 12px;
    color: #FFF;
    background: #1B264F;
    text-align: center;
    font-family: 'Poppins', sans-serif;
    font-size: 17px;
    font-style: normal;
    font-weight: 700;
    line-height: 60px;
    letter-spacing: 3.4px;
    text-transform: uppercase;
}
</style>
