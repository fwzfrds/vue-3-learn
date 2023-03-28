<template>
  <div>
    <input type="text" placeholder="Name" v-model="name" />

    <input type="text" placeholder="First Name" v-model="firstName" />
    <input type="text" placeholder="Last Name" v-model="lastName" />

    <input type="text" placeholder="Reactive First Name" v-model="fName" />
    <input type="text" placeholder="Reactive Last Name" v-model="lName" />
    <input
      type="text"
      placeholder="Reactive Hero Name"
      v-model="options.heroName"
    />
    <input type="text" placeholder="Address" v-model="options.address" />
  </div>
</template>

<script>
import { ref, watch, reactive, toRefs } from "vue";
import _ from "lodash";

export default {
  name: "WatchComp",
  setup() {
    const state = reactive({
      fName: "",
      lName: "",
      options: {
        heroName: "",
        address: "",
      },
    });

    // watch(
    //   () => {
    //     return { ...state };
    //   },
    //   (newValue, oldValue) => {
    //     console.log("fName oldValue", oldValue.fName);
    //     console.log("fName newValue", newValue.fName);
    //     console.log("lName oldValue", oldValue.lName);
    //     console.log("lName newValue", newValue.lName);
    //   }
    // );

    watch(
      () => _.cloneDeep(state.options),
      function (newValue, oldValue) {
        console.log("fName oldValue", oldValue);
        console.log("fName newValue", newValue);
      },
      {
        deep: true,
      }
    );

    const firstName = ref("");
    const lastName = ref("Wayne");

    watch(
      [firstName, lastName],
      (newValues, oldValues) => {
        console.log("firstName Old Value", oldValues[0]);
        console.log("firstName New Value", newValues[0]);
        console.log("lastName Old Value", oldValues[1]);
        console.log("lastName New Value", newValues[1]);
      },
      {
        immediate: true,
      }
    );

    return {
      firstName,
      lastName,
      ...toRefs(state),
    };
  },
  data() {
    return {
      name: "",
    };
  },
  watch: {
    name(newValue, oldValue) {
      console.log("Old Value", oldValue);
      console.log("New Value", newValue);
    },
  },
};
</script>

<style scoped>
</style>