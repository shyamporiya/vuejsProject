<template>
  <div>
    <h1>Computed Prop</h1>
    <input v-model="live_search" />
    <span>{{ dataSearch }}</span>
  </div>
</template>
<script>
export default {
  name: "App",
  components: {},
  data() {
    return {
      live_search: "hello",
      bulk_text: [
        { name: "test", hobby: "cricket" },
        { name: "test_123", hobby: "cricket_123" },
        { name: "test_456", hobby: "cricket_456" },
      ],
    };
  },
  computed: {
    dataSearch() {
      if (this.live_search) {
        return this.live_search.filter((item) => {
          return this.live_search
            .toLocaleLowerCase()
            .split(" ")
            .every((v) => item.name.toLocaleLowerCase().includes(v));
        });
      } else {
        return this.live_search;
      }
      return; // alert("hello");
    },
  },
  methods: {},
};
</script>
