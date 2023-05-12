<template>
  <h1>V-if condition</h1>

  <button @click="show_div">click to show if condition div</button>
  <div v-if="ifexample">
    <p>This is if condition div</p>
  </div>
  <div v-else-if="isName">
    <p>This is else if condition div</p>
  </div>
  <div v-else>
    <p>this is else div</p>
  </div>

  <h1>V-Show Example</h1>
</template>

<script>
import Header from "./components/HeaderTitle.vue";
import structure_div from "./components/Structure.vue";

export default {
  name: "App",
  components: {},
  props: {},
  data() {
    return {
      ifexample: false,
      isName: true,
      // showExample: true,
    };
  },
  methods: {
    show_div() {
      this.ifexample = true;
    },
  },
};
</script>
