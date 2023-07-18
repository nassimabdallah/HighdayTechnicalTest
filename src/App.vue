<template>
  <div>
    <Header />
    <DateNavigation />
    <Suspense>
      <Tasks />
      <template #fallback>
        <TaskCardSkeleton />
      </template>
    </Suspense>
  </div>
</template>

<script setup>
import Header from './components/Header.vue'
import DateNavigation from './components/DateNavigation.vue'
import Tasks from './components/Tasks.vue';
import TaskCardSkeleton from './components/TaskCardSkeleton.vue';
</script>

<style lang="scss" scoped></style>