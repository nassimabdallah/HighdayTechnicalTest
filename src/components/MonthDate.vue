<template>
    <div class="day">
        <span class="is-size-5 has-text-weight-bold">{{ day }}</span>
        <span class="is-size-7">{{ label }}</span>
    </div>
</template>

<script setup>
defineProps({
    day: {
        type: Number,
        default: 1
    },
    label: {
        type: String,
        default: "Mon"
    }
});
</script>

<style lang="scss" scoped>
@import "../assets/variable.scss";
.day {
    display: flex;
    flex-direction: column;
    justify-content: center;
    align-items: center;
    width: 20%;
    height: 90px;
    border-radius: 30px;
    background-color: #fff;
    color: $primary;
}
</style>