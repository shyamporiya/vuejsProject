<template>
  <Header />
  <Content />

  <!-- <modal /> -->
</template>

<script>
import Header from "./components/body/Header.vue";
import Content from "./components/body/Content.vue";
import Footer from "./components/body/Footer.vue";
import modal from "./components/V-modelExample.vue";
import addOrRemove from "./components/addRoomOrProduct.vue";

export default {
  name: "App",
  components: { Header, Content, Footer, modal, addOrRemove },
  data() {
    return {};
  },
  methods: {},
};
</script>
