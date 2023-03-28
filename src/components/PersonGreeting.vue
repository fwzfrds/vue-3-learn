<template>
  <div>Hello {{ fullName }}</div>
  <button @click="sendEvent">Call Heroes</button>
</template>

<script>
import { computed } from "vue";

export default {
  name: "PersonGreeting",
  emits: ["callHeroes"], // <--- add this line
  setup(props, context) {
    console.log(context);
    const fullName = computed(() => {
      //   const { firstName, lastName } = props;
      return `${props.firstName} ${props.lastName}`;
      //   return `${firstName} ${lastName}`;
    });

    function sendEvent() {
      context.emit("callHeroes", fullName.value);
    }

    return {
      fullName,
      sendEvent,
    };
  },
  props: ["firstName", "lastName"],
  //   computed: {
  //     fullName() {
  //       return `${this.firstName} ${this.lastName}`;
  //     },
  //   },
};
</script>

<style scoped>
</style>