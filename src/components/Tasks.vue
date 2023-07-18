<template>
    <section class="task-navigation px-2">
        <h1 class="is-size-4 has-text-weight-bold my-2">Ongoing</h1>
        <div class="work-schedule mt-2">
            <div class="timeline">
                <span v-for="time in timeObj" class="is-size-7">{{ time.strTime }}</span>
            </div>
            <div class="tasks">
                <TaskCard 
                    v-for="task in dailyTasks" 
                    :key="task" 
                    :task="task"
                    :style="{'grid-row-start': task.start_time.split(':')[0], 'grid-row-end': task.end_time.split(':')[0]}" 
                />
            </div>
        </div>
    </section>
</template>

<script setup>
import TaskCard from './TaskCard.vue';
import axios from 'axios';
import { ref, computed } from 'vue';

const tasks = ref([]);
const dailyTasks = ref([]);
const date = ref(new Date('2023-07-17').toLocaleDateString('fr-FR'))
const timeObj = ref([]);
const timelineLength = timeObj.value.length;

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

const timelineSchedule = computed(() => {
    const start = Math.min(...dailyTasks.value.map(task => parseInt(task.start_time)));
    const end = Math.max(...dailyTasks.value.map(task => parseInt(task.end_time)));
    return {start, end}
})

const getTimeline = () => {
    let obj = {};
    let id = 1;
    for (let i = timelineSchedule.value.start; i <= timelineSchedule.value.end; i++) {
        let ampm = i >= 12 ? 'PM' : 'AM';
        let hour = i % 12;
        hour = hour ? hour : 12;
        let strTime = `${hour} ${ampm}`;
        obj[i] = {id, strTime}
        id++;
    }
    timeObj.value = obj;
}

getTimeline();
console.log(timeObj.value);

</script>

<style lang="scss" scoped>
$timelineLength: v-bind(timelineLength);

.work-schedule {
    display: grid;
    gap: 10px;
    grid-template-columns: auto 1fr;
}

.timeline {
    display: grid;
    grid-template-rows: repeat($timelineLength);
    align-items: center;
}

.tasks {
    display: grid;
    grid-template-rows: repeat($timelineLength);
}
</style>