<template>
    <header class="is-mobile is-flex is-justify-content-space-between is-align-items-center">
        <div>
            <button class="button is-transparent">
                <span class="icon">
                    <i class="fa-solid fa-arrow-left"></i>
                </span>
            </button>
        </div>
        <div class="logo is-flex">
            <a>
                <i class="highday-logo"></i>
            </a>
        </div>
        <Suspense>
            <ProfilePicture />
            <template #fallback>
                <ProfilePictureSkeleton />
            </template>
        </Suspense>
    </header>
</template>

<script setup>
import ProfilePicture from './ProfilePicture.vue';
import ProfilePictureSkeleton from './ProfilePictureSkeleton.vue';
</script>

<style lang="scss" scoped>
header .logo {
    border: 1px solid hsl(0, 0%, 86%);
    border-radius: 50%;
    padding: 10px;
}
</style>