<template>
  <div>Composition API Lifescycle Hooks</div>
</template>

<script>
import {
  onBeforeMount,
  onMounted,
  onBeforeUpdate,
  onUpdated,
  onBeforeUnmount,
  onUnmounted,
} from "vue";

export default {
  name: "LifeCycleC",
  setup() {
    onBeforeMount(() => {
      console.log("LifeCycleC beforeMount()");
    });
    onMounted(() => {
      console.log("LifeCycleC mounted()");
    });
    onBeforeUpdate(() => {
      console.log("LifeCycleC beforeUpdate()");
    });
    onUpdated(() => {
      console.log("LifeCycleC updated()");
    });
    onBeforeUnmount(() => {
      console.log("LifeCycleC beforeUnmount()");
    });
    onUnmounted(() => {
      console.log("LifeCycleC unmounted()");
    });
  },
};
</script>

<style scoped>
</style>