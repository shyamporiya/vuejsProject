<template>
  <section class="main-section">
    <div>
      <h1>Welcome To Vue Js</h1>
      <h3>Task</h3>
    </div>
    <div>
      <button class="add_another_room" @click="add_another_room">
        Add room
      </button>
      <button class="remove_another_room" @click="remove_another_room">
        Remove room
      </button>
    </div>
    <div class="table_room" v-for="(elem, index) in roomCount" :key="index">
      <span class="room-name">Room {{ index }}</span>
      <div class="adult">
        <span class="adultName">Adult</span>
        <div class="add_div">
          <button @click="adultDecBtn">-</button>
          <span>{{ adultRoomCount }}</span>
          <button @click="adultIncBtn">+</button>
        </div>
      </div>
      <div class="add_child_div">
        <span class="childName">Child</span>
        <div class="sub_child_div">
          <button @click="childDecBtn">-</button>
          <span>{{ childRoomCount }}</span>
          <button @click="childIncBtn">+</button>
        </div>
      </div>
    </div>
    <hr />
  </section>
  <section>
    <div class="parent-div">
      <button class="addMorecol" @click="addColums()">Add More</button>
      <table style="width: 30%">
        <tr>
          <th>Product Name</th>
          <th>Category</th>
          <th>Price</th>
          <th>Discount</th>
          <th>Total</th>
        </tr>
        <tr v-for="(col, index) in colums" :key="index">
          <td>
            <input
              style="width: 135px"
              type="text"
              placeholder="Product Name"
              v-model="productName"
            />
          </td>
          <td>
            <select
              style="border: 2px solid black; width: 100px"
              v-model="categoryName"
            >
              <option value="">Select</option>
              <option value="average">Average</option>
              <option value="good">Good</option>
              <option value="bad">Bad</option>
              <option value="nonuse">Non-use</option>
            </select>
          </td>
          <td>
            <input
              style="width: 70px"
              type="text"
              placeholder="price"
              v-model="price"
              @input="priceOnchange()"
              id="price"
            />
          </td>
          <td>
            <input
              style="width: 100px"
              type="text"
              placeholder="Discount %"
              v-model="discount"
              id="discount"
              @input="discountOnchange()"
            />
          </td>
          <td>
            <!-- <input
              style="width: 60px"
              type="text"
              placeholder="Total"
              v-model="sum"
            /> -->
            <h5>{{ sum }}</h5>
          </td>
          <td><button @click="submitBtn()">Submit</button></td>
        </tr>
      </table>
    </div>
  </section>
  <hr />
  <section>
    <h5>Record Of Table</h5>
    <div class="parent-div">
      <table style="width: 30%">
        <tr>
          <th>Product Name</th>
          <th>Category</th>
          <th>Price</th>
          <th>Discount</th>
          <th>Total</th>
        </tr>
        <tr>
          <td>
            {{ productNameGet }}
          </td>
          <td>{{ categoryNameGet }}</td>
          <td>{{ priceGet }}</td>
          <td>{{ discountGet }}</td>
          <td>{{ totalGet }}</td>
        </tr>
      </table>
    </div>
  </section>
</template>
<script>
export default {
  name: "App",
  components: {},
  data() {
    return {
      adultRoomCount: 1,
      childRoomCount: 1,
      roomCount: 1,
      colums: 1,
      productName: "",
      productNameGet: "",
      categoryName: "",
      categoryNameGet: "",
      price: "",
      priceGet: "",
      discount: "",
      discountGet: "",
      total: "",
      totalGet: "",
      sum: "",
      productData: [
        { product: "Test 1 ", category: "Main" },
        { product: "test 2", category: "cat test" },
        { product: "productName", category: "test1" },
        { product: "productName", category: "test1" },
        { product: "productName", category: "test1" },
      ],
    };
  },
  methods: {
    adultDecBtn() {
      this.adultRoomCount--;
    },
    adultIncBtn() {
      this.adultRoomCount++;
    },
    childDecBtn() {
      this.childRoomCount--;
    },
    childIncBtn() {
      this.childRoomCount++;
    },
    add_another_room() {
      this.roomCount++;
      console.log(this.roomCount);
    },
    remove_another_room() {
      this.roomCount--;
    },
    addColums() {
      this.colums++;
      console.log("click here to add colums");
    },
    submitBtn() {
      console.log("Submit Clicked");
      var listData = this.productData.map((index, val, arr) => {
        return index.product;
        console.log("index" + index);
      });
      this.productNameGet = this.productName;
      this.categoryNameGet = this.categoryName;
      this.priceGet = this.price;
      this.discountGet = this.discount;
      this.totalGet = this.total;
      console.log(this.productNameGet);
    },
    priceOnchange() {
      console.log("hello");
      // var pricecal = this.price;
      // var dis_cal = this.discount;
      // var sum = "hello";
      // console.log(sum);

      var pricecal = document.getElementById("price").value;
      var dis_cal = document.getElementById("discount").value;

      // Add them together and display
      var sum = parseInt(pricecal) + parseInt(dis_cal);
    },
    discountOnchange() {
      console.log("hello");
      // var pricecal = this.price;
      // var dis_cal = this.discount;
      // var sum = "hello";
      // console.log(sum);

      var pricecal = document.getElementById("price").value;
      var dis_cal = document.getElementById("discount").value;

      // Add them together and display
      var sum_value = parseInt(pricecal) + parseInt(dis_cal);
      this.sum = sum_value;
    },
  },
};
</script>

<style scoped>
button {
  border: 2px solid black;
  background: burlywood;
}
.table_room {
  border: 2px solid black;
  /* margin-left: 473px; */
  height: 140px;
  width: 290px;
  background-color: aliceblue;
}
.room-name {
  margin-left: 100px;
  font-size: 22px;
  font-weight: 700;
  font-family: fangsong;
  border: 2px solid black;
}
.adult {
  margin-left: 5px;
  /* border: 2px solid black; */
  margin-right: 22px;
  margin-top: 12px;
}
.add_div {
  margin-left: -4px;
  margin-top: 6px;
}
.add_child_div {
  margin-left: 175px;
  margin-top: -60px;
}
.adultName {
  font-size: 22px;
  font-weight: 700;
  font-family: fangsong;
  border: 2px solid black;
}
.childName {
  font-size: 22px;
  font-weight: 700;
  font-family: fangsong;
  border: 2px solid black;
}
.add_another_room {
  margin-left: 205px;
  margin-bottom: 4px;
}
.main-section {
  margin-left: 10px;
}
table,
th,
td {
  border: 1px solid black;
  width: fit-content;
}
.addMorecol {
  margin-left: 465px;
}
</style>
