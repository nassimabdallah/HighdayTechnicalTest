<template>
    <section class="task-navigation px-2">
        <h1 class="is-size-4 has-text-weight-bold my-2">Ongoing</h1>
        <TaskCard
            v-for="task in dailyTasks"
            :key="task"
            :task="task"
        />
    </section>
</template>

<script setup>
import TaskCard from './TaskCard.vue';
import axios from 'axios';
import { ref } from 'vue';

const tasks = ref([]);
const dailyTasks = ref([]);
const date = ref(new Date('2023-07-17').toLocaleDateString('fr-FR'))

const getTasks = async () => {
    try {
        const userData = await axios.get('./data/tasks.json')
        return userData.data.tasks
    } catch (error) {
        console.error(error)
    }
}

tasks.value = await getTasks();

// Get tasks for the day selected only
const getDailyTasks = () => {
    return tasks.value.filter(dateTask => dateTask.date === date.value)
}

dailyTasks.value = getDailyTasks()

</script>

<style lang="scss" scoped>

</style>