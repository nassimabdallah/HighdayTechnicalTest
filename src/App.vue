<template>
  <div class="bg-main is-fullscreen pb-2">
    <Header />
    <DateNavigation />
    <Suspense>
      <Tasks />
      <template #fallback>
        Loading...
      </template>
    </Suspense>
  </div>
</template>

<script setup>
import Header from './components/Header.vue'
import DateNavigation from './components/DateNavigation.vue'
import Tasks from './components/Tasks.vue';
</script>

<style lang="scss" scoped></style>