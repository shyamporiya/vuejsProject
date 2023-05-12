<script setup>
defineProps({
  msg: {
    type: String,
    required: true,
  },
});
</script>

<template>
  <div class="hello">
    <h1>{{ userName }}</h1>
    <h1>{{ userEmail }}</h1>
    <button className="clickMe" @click="click_me">Click Me</button>
    <p>
      For a guide and recipes on how to configure / customize this project,<br />
      check out the
      <a href="https://cli.vuejs.org" target="_blank" rel="noopener"
        >vue-cli documentation</a
      >.
    </p>
    <h3>Installed CLI Plugins</h3>
    <ul>
      <li>
        <a
          href="https://github.com/vuejs/vue-cli/tree/dev/packages/%40vue/cli-plugin-babel"
          target="_blank"
          rel="noopener"
          >babel</a
        >
      </li>
      <li>
        <a
          href="https://github.com/vuejs/vue-cli/tree/dev/packages/%40vue/cli-plugin-eslint"
          target="_blank"
          rel="noopener"
          >eslint</a
        >
      </li>
    </ul>
    <h3>Essential Links</h3>
    <ul>
      <li>
        <a href="https://vuejs.org" target="_blank" rel="noopener">Core Docs</a>
      </li>
      <li>
        <a href="https://forum.vuejs.org" target="_blank" rel="noopener"
          >Forum</a
        >
      </li>
      <li>
        <a href="https://chat.vuejs.org" target="_blank" rel="noopener"
          >Community Chat</a
        >
      </li>
      <li>
        <a href="https://twitter.com/vuejs" target="_blank" rel="noopener"
          >Twitter</a
        >
      </li>
      <li>
        <a href="https://news.vuejs.org" target="_blank" rel="noopener">News</a>
      </li>
    </ul>
    <h3>Ecosystem</h3>
    <ul>
      <li>
        <a href="https://router.vuejs.org" target="_blank" rel="noopener"
          >vue-router</a
        >
      </li>
      <li>
        <a href="https://vuex.vuejs.org" target="_blank" rel="noopener">vuex</a>
      </li>
      <li>
        <a
          href="https://github.com/vuejs/vue-devtools#vue-devtools"
          target="_blank"
          rel="noopener"
          >vue-devtools</a
        >
      </li>
      <li>
        <a href="https://vue-loader.vuejs.org" target="_blank" rel="noopener"
          >vue-loader</a
        >
      </li>
      <li>
        <a
          href="https://github.com/vuejs/awesome-vue"
          target="_blank"
          rel="noopener"
          >awesome-vue</a
        >
      </li>
    </ul>
  </div>
</template>

<script>
export default {
  name: "HelloWorld",
  props: {
    msg: String,
  },
  data() {
    return {
      userName: "Shyam Poriya",
      userEmail: "shyamporiya9595@gmail.com",
      userId: "",
      count: 0,
      obj: [
        { state: "Gujarat", city: "Ahmedabad" },
        { state: "Maharashtra", city: "Pune" },
        { state: "Rajasthan", city: "Jaipur" },
      ],
      dataList: [],
      filterData: [],
      vIf: true,
    };
  },
  methods: {
    click_me() {
      console.log("this", this);
      this.userId = "shyam_poriya";
      this.count = 220;
    },
    /* onAlert() {
      alert("hello world!!");
    },
    onShowData() {
      const newArray = this.obj.map((elm, index, arr) => {
        return elm.name;
      });
      this.dataList = newArray;
      console.log("newArray", newArray);
    },
    onFilterData() {
      const newFilterlist = this.obj.filter((item, index, arr) => {
        return item.age > 22;
      }); 
      this.filterData = newFilterlist;
      console.log("newFilterlist", newFilterlist);
    },
    */
  },
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
h3 {
  margin: 40px 0 0;
}
ul {
  list-style-type: none;
  padding: 0;
}
li {
  display: inline-block;
  margin: 0 10px;
}
a {
  color: #42b983;
}
.clickMe:hover {
  background-color: blue;
  border: 2px solid red;
}
</style>
