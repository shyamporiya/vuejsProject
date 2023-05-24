<template>
  <Header />

  <Product_List />

  <!-- <modal /> -->
</template>

<script>
import Header from "./components/body/Header.vue";
import Content from "./components/body/Content.vue";
import Footer from "./components/body/Footer.vue";
import modal from "./components/V-modelExample.vue";
import Product_List from "./components/Product_List.vue";
import computed_prop from "./components/Computed_Prop.vue";

export default {
  name: "App",
  components: {
    Header,
    Content,
    Footer,
    modal,
    computed_prop,
    Product_List,
  },
  data() {
    return {};
  },
  methods: {},
};
</script>
