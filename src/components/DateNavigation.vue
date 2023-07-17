<template>
    <section class="month-navigation">
        <div class="is-flex is-justify-content-space-between is-align-items-center p-2">
            <div>
                <span class="icon">
                    <i class="fa-solid fa-arrow-left"></i>
                </span>
                <span class="is-size-7"> Jun </span>
            </div>
            <div class="is-size-3 has-text-weight-semibold has-text-centered">
                <p>July</p>
            </div>
            <div>
                <span class="is-size-7"> Aug </span>
                <span class="icon">
                    <i class="fa-solid fa-arrow-right"></i>
                </span>
            </div>
        </div>
    </section>
    <section class="day-navigation is-flex is-flex-direction-row is-justify-content-space-around is-align-items-center p-4">
        <MonthDate 
            v-for="day in days"
            :key="day"
            :day="day.day"
            :label="day.label"
            :class="{active: day.day === 17}"
        />
    </section>
</template>

<script setup>
import { ref } from 'vue';
import MonthDate from './MonthDate.vue';
const days = ref([
    {
        day: 17,
        label: "Mon"
    },
    {
        day: 18,
        label: "Tue"
    },
    {
        day: 19,
        label: "Wed"
    },
    {
        day: 20,
        label: "Thu"
    },
])

</script>

<style lang="scss" scoped>
@import "../assets/variable.scss";
.month-navigation {
    .icon {
        font-size: 0.9rem;
    }
}
.active {
    background-color: $primary;
    color: white;
}
</style>