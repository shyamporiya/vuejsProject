<template>
  <Header />
  <Content />
  <Footer />
</template>

<script>
import Header from "./components/body/Header.vue";
import Content from "./components/body/Content.vue";
import Footer from "./components/body/Footer.vue";

export default {
  name: "App",
  components: { Header, Content, Footer },
  data() {
    return {};
  },
  methods: {},
};
</script>
