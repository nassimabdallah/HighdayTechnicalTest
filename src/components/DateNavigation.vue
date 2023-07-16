<template>
    <section class="month-navigation">
        <div class="is-flex is-justify-content-space-between is-align-items-center p-2">
            <div>
                <span class="icon">
                    <i class="fa-solid fa-arrow-left"></i>
                </span>
            </div>
            <div class="is-size-3 has-text-weight-semibold has-text-centered">
                <p>July</p>
            </div>
            <div>
                <span class="icon">
                    <i class="fa-solid fa-arrow-right"></i>
                </span>
            </div>
        </div>
    </section>
    <section class="day-navigation is-flex is-flex-direction-row is-justify-content-space-around is-align-items-center p-4">
        <MonthDate />
        <MonthDate />
        <MonthDate />
        <MonthDate />
    </section>
</template>

<script setup>
import MonthDate from './MonthDate.vue';


</script>

<style lang="scss" scoped>
.month-navigation {
    .icon {
        font-size: 0.9rem;
    }
}
</style>