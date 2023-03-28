<template>
  <h2>Options - {{ o_firtsName }}</h2>
  <h2>Options - {{ o_firtsName }} {{ o_lastName }} a.k.a {{ o_heroName }}</h2>

  <h2>Composition - {{ c_firtsName }}</h2>
  <h2>Composition - {{ greet }}</h2>

  <h2>Composition - {{ c_firtsName }} {{ c_lastName }} {{ c_heroName }}</h2>
  <h2>Composition - {{ greetHero }}</h2>

  <h2>
    Composition {{ state.firstName }} {{ state.lastName }} {{ state.heroName }}
  </h2>
  <h2>Composition - {{ reactiveGreetGero }}</h2>
</template>

<script>
import { ref, reactive } from "vue";

export default {
  name: "DataComp",
  setup() {
    const c_firtsName = ref("Clark");
    const c_lastName = ref("Kent");
    const c_heroName = ref("Superman");

    const greet = `Hello ${c_firtsName.value}`;
    const greetHero = `Hello ${c_firtsName.value} ${c_lastName.value} a.k.a ${c_heroName.value}`;

    const state = reactive({
      firstName: "Princess",
      lastName: "Diana",
      heroName: "Wonder Woman",
    });

    const reactiveGreetGero = `Hello ${state.firstName} ${state.lastName} a.k.a ${state.heroName}`;

    return {
      c_firtsName,
      c_lastName,
      c_heroName,
      greet,
      greetHero,
      state,
      reactiveGreetGero,
    };
  },
  data() {
    return {
      o_firtsName: "Bruce",
      o_lastName: "Wayne",
      o_heroName: "Batman",
    };
  },
};
</script>

<style scoped>
</style>