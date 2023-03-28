<template>
  <h3>Parent Component {{ name }}</h3>
  <h3>Parent Component count {{ count }}</h3>
  <h3>Parent Component hero {{ firstName }} {{ lastName }}</h3>

  <button @click="incrementCount">Increment count</button>
  <ChildA />
</template>

<script>
import { provide, ref, reactive, toRefs } from "vue";
import ChildA from "./ChildA";

export default {
  name: "ProvideInject",
  components: {
    ChildA,
  },
  setup() {
    provide("c_userName", "Codevolution");

    const count = ref(0);
    function incrementCount() {
      count.value++;
    }

    const state = reactive({
      firstName: "Bruce",
      lastName: "Wayne",
    });

    provide("c_count", count);
    provide("c_hero", state);
    provide("incrementCount", incrementCount);

    return {
      count,
      ...toRefs(state),
      incrementCount,
    };
  },
  data() {
    return {
      name: "Fawwaz",
    };
  },
  provide() {
    return {
      userName: this.name,
    };
  },
};
</script>

<style scoped>
</style>