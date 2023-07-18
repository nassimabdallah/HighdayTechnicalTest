<template>
    <section class="task-navigation px-2">
        <h1 class="is-size-4 has-text-weight-bold my-2">Ongoing</h1>
        <div class="is-flex is-flex-direction-column task-card p-3">
            <AnimatedPlaceholder class="task-title"/>
            <AnimatedPlaceholder class="user-name"/>
            <div class="is-flex is-justify-content-space-between is-align-items-center mt-2">
                <AnimatedPlaceholder class="image-circle-placeholder"/>
                <AnimatedPlaceholder class="user-name"/>
            </div>
        </div>
    </section>
</template>

<script setup>
import AnimatedPlaceholder from './AnimatedPlaceholder.vue';
</script>

<style lang="scss" scoped>
@import '../assets/variable.scss';
.task-card {
    height: 106px;
    border-radius: 15px;
    background-color: hsl(0, 0%, 93%);
    color: #fff;
}
.image-circle-placeholder {
    width: 32px;
    height: 32px;
    border: 2px solid hsl(0, 0%, 86%);
    border-radius: 50%;
}
.user-name {
    height: 0.75rem;
    width: 40%;
    margin: 1px 0;
}
.task-title {
    height: 1rem;
    margin: 5px 0;
}
</style>