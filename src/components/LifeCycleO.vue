<template>
  <div>Options API Lifescycle Hooks</div>
</template>

<script>
export default {
  name: "LifeCycleO",
  beforeCreate() {
    console.log("LifeCycleO beforeCreate()");
  },
  created() {
    console.log("LifeCycleO crated()");
  },
  beforeMount() {
    console.log("LifeCycleO beforeMount()");
  },
  mounted() {
    console.log("LifeCycleO mounted()");
  },
  beforeUpdate() {
    console.log("LifeCycleO beforeUpdate()");
  },
  updated() {
    console.log("LifeCycleO updated()");
  },
  beforeUnmount() {
    console.log("LifeCycleO beforeUnmount()");
  },
  unmounted() {
    console.log("LifeCycleO unmounted()");
  },
};
</script>

<style scoped>
</style>