<template>
  <div>
    <h1>Welcome To Vue Js</h1>
    <h3>Example of Increment Or Decrement</h3>
    <hr />
    <input
      type="number"
      class="value-text"
      placeholder="Enter Value"
      v-model="countVal"
    />
    <button class="btn btn-success" @click="addVal()">Add Value</button>
    <hr />
    <button class="increment-btn btn btn-primary" @click="inc_btn()">
      <i style="inc-btn">+</i>
    </button>

    <span type="number" class="showCount">{{ count }}</span>
    <button class="decrement-btn btn btn-warning" @click="dect_btn()">
      <i class="dec-btn">-</i>
    </button>
    <hr />
  </div>
</template>
<script>
export default {
  name: "App",
  component: {},
  data() {
    return {
      count: "",
      countVal: "",
    };
  },
  methods: {
    addVal() {
      this.count = this.countVal;
    },

    inc_btn() {
      console.log(" increment clicked");
      this.count++;
      if (this.count <= 0) {
        console.log("only 0");
      } else {
        // this.example_values++;
      }
    },
    dect_btn() {
      console.log("decrement clicked");
      if (this.count !== this.countVal && this.count !== 0) {
        // /alert("Minimum Value Is 0");
        //  console.log("worked");
        this.count--;
      } else if (this.count === this.countVal) {
        alert("Your Value Is : " + this.countVal + " You Can't Decrement");
      } else if (this.count === 0) {
        alert("Minimum Value 0");
      }
    },
  },
};
</script>

<style scoped>
.increment-btn,
.decrement-btn {
  border: 2px solid rgb(7, 10, 0);
}
.value-text {
  margin-right: 25px;
}
.showCount {
  padding: 2px 27px 8px 28px;
  border: 3px solid black;
  font-weight: 700;
}
</style>
>
