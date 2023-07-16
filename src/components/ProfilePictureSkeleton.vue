<template>
    <div class="is-flex is-flex-direction-column is-align-items-center">
        <AnimatedPlaceholder class="image-circle-placeholder"/>
        <AnimatedPlaceholder class="user-name"/>
        <AnimatedPlaceholder class="user-name"/>
    </div>
</template>

<script setup>
import AnimatedPlaceholder from './AnimatedPlaceholder.vue';
</script>

<style lang="scss" scoped>
.image-circle-placeholder {
    width: 48px;
    height: 48px;
    border: 1px solid hsl(0, 0%, 86%);
    border-radius: 50%;
}
.user-name {
    height: 0.75rem;
    margin: 1px 0;
}
</style>