<template>
  <div>
    <TopSiteNavigation />
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
import TopSiteNavigation from './components/TopSiteNavigation.vue';
import DateNavigation from './components/DateNavigation.vue';
import Tasks from './components/Tasks.vue';
import TaskCardSkeleton from './components/TaskCardSkeleton.vue';
</script>