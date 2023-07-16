<template>
    <div class="is-flex is-flex-direction-column is-align-items-center">
        <figure class="image is-48x48">
            <img class="is-rounded" :src="userData.avatar_url">
        </figure>
        <div class="has-text-weight-medium has-text-centered is-size-7">
            <p>{{ userData.first_name }}</p>
            <p class="is-uppercase">{{ userData.last_name }}</p>
        </div>
    </div>
</template>

<script setup>
import axios from 'axios'

const getUser = async () => {
    try {
        const userData = await axios.get('./data/tasks.json')
        return userData.data
    } catch (error) {
        console.error(error)
    }
}

const userData = await getUser()

</script>

<style lang="scss" scoped>
p{
    line-height: 1;
}
</style>