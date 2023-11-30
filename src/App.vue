<template>
  <HelloWorld msg="prop data method" />
  <LifeCycleVue />
  <ComputedVue/>
  <ParentComponent/>
</template>

<script setup>
import ComputedVue from "./components/Computed.vue";
import HelloWorld from "./components/HelloWorld.vue";
import LifeCycleVue from "./components/LifeCycle.vue";
import ParentComponent from "./components/ParentComponent.vue"
</script>

<style scoped>
.logo {
  height: 6em;
  padding: 1.5em;
  will-change: filter;
  transition: filter 300ms;
}
.logo:hover {
  filter: drop-shadow(0 0 2em #646cffaa);
}
.logo.vue:hover {
  filter: drop-shadow(0 0 2em #42b883aa);
}
</style>
