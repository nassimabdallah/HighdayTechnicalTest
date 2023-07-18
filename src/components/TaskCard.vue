<template>
    <div class="is-flex is-flex-direction-column task-card p-3 mb-2">
        <p>{{ task.title }}</p>
        <p class="is-size-7 mb-2">{{ getMembersTask() }}</p>
        <div class="is-flex is-justify-content-space-between is-align-items-center">
            <div class="task-avatar">
                <figure 
                    v-for="(member, index) in task.members"
                    :key="index"
                    class="image is-32x32"
                    :style="{ left: index * 25 + 'px' }"
                >
                    <img class="is-rounded" :src="member.avatar_url">
                </figure>
            </div>
            <p class="is-size-7">{{ formatAMPM(task.start_time) }} - {{ formatAMPM(task.end_time) }}</p>
        </div>
    </div>
</template>

<script setup>
const props = defineProps({
    task: {
        type: Object,
        default: null
    }
});

const getMembersTask = () => {
    const members = props.task.members.map(member => member.name);
    const lastMember = members.pop();
    return members.join(", ") + ' and ' + lastMember;
};

const formatAMPM = (time) => {
    let [ hour, minutes ] = time.split(':');
    const ampm = hour >= 12 ? 'PM' : 'AM';
    hour = hour % 12;
    hour = hour ? hour : 12; // the hour '0' should be '12'
    const strTime = hour + ':' + minutes + ' ' + ampm;
    return strTime;
};

</script>

<style lang="scss" scoped>
@import "../assets/variable.scss";

.task-card {
    border-radius: 15px;
    background-color: $primary;
    color: #fff;
}

.task-avatar {
    position: relative;
    height: 32px;

    figure {
        position: absolute;
        border: 2px solid #fff;
        border-radius: 50%;
    }
}
</style>