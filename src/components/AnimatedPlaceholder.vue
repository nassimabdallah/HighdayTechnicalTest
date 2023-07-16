<template>
    <div class="load-wraper">
        <div class="activity"></div>
    </div>
</template>

<script setup></script>

<style lang="scss" scoped>
.load-wraper{
  position: relative;
  height: 100%;
  width: 100%;
  background-color: rgb(211,211,211);
  z-index: 44;
  overflow: hidden;
  border-radius: 5px;

  .activity{
    position: absolute;
    left: -45%;
    top: 0;
    height: 100%;
    width: 45%;
    background: rgb(211,211,211);
    background: -moz-linear-gradient(to left, rgba(211,211,211,1), rgb(197,197,197,1), rgb(211,211,211,1));
    background: -webkit-linear-gradient(to left, rgba(211,211,211,1), rgba(197,197,197,1), rgba(211,211,211,1));
    background: linear-gradient(to left, rgba(211,211,211,1), rgba(197,197,197,1), rgba(211,211,211,1));
    animation: loading 1s infinite;
    z-index: 45;
    }
}


@keyframes loading {
  0%{
    left: -45%;
  }
  100%{
    left: 100%;
  }
}
</style>