<template>
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
        <tr v-for="(col, index) in productList" :key="index">
          <td>
            <input
              style="width: 135px"
              type="text"
              placeholder="Product Name"
              id="product_name_{{index}}"
              v-model="col.productName"
            />
          </td>

          <td>
            <select
              style="border: 2px solid black; width: 100px"
              id="category_name"
              v-model="col.categoryName"
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
              type="number"
              placeholder="price"
              v-model="col.price"
              id="price_val"
              @input="discountOnchange(col)"
            />
          </td>
          <td>
            <input
              style="width: 100px"
              type="number"
              placeholder="Discount %"
              id="dis_val"
              v-model="col.discount"
              @input="discountOnchange(col)"
            />
          </td>
          <td>
            <input
              style="width: 60px"
              type="text"
              placeholder="Total"
              disabled
              id="total_val"
              v-model="col.total"
            />
          </td>
          <td><button @click="removeBtn()">Remove</button></td>
        </tr>
      </table>
    </div>
    <div>
      <button class="submitEvent" @click="submitBtn()">Submit</button>
    </div>
  </section>
  <hr />
  <section>
    <h5>Record Of Table</h5>
    <div class="">
      <table style="width: 30%">
        <tr>
          <th style="width: 20px">Product Name</th>
          <th style="width: 20px">Category</th>
          <th style="width: 20px">Price</th>
          <th style="width: 20px">Discount</th>
          <th style="width: 20px">Total</th>
        </tr>
        <tr v-for="(col, index) in getList" :key="index">
          <td>
            <input
              style="width: 115px"
              type="text"
              id=""
              readonly="true"
              v-model="col.productName"
            />
          </td>
          <td>
            <input
              style="width: 115px"
              type="text"
              id=""
              readonly="true"
              v-model="col.categoryName"
            />
          </td>
          <td>
            <input
              style="width: 115px"
              type="number"
              id="product_name"
              readonly="true"
              v-model="col.price"
            />
          </td>
          <td>
            <input
              style="width: 115px"
              type="text"
              readonly="true"
              v-model="col.discount"
            />
          </td>
          <td>
            <input
              style="width: 115px"
              type="text"
              id=""
              readonly="true"
              v-model="col.total"
            />
          </td>
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
      testing: "hello465465546",
      rooms: [
        {
          //room_No: 1,
          adult_count: 1,
          child_count: 0,
        },
      ],
      productList: [
        {
          productName: "",
          categoryName: "",
          price: "",
          discount: "",
          total: "",
        },
      ],
      getList: [
        {
          productName: "",
          categoryName: "",
          price: "",
          discount: "",
          total: "",
        },
      ],
    };
  },
  methods: {
    addColums() {
      this.productList.push({
        productName: null,
        categoryName: null,
        price: null,
        discount: null,
        total: null,
      });
    },
    removeBtn() {
      if (this.productList.length > 1) {
        this.productList.pop({
          productName: "",
          categoryName: "",
          price: "",
          discount: "",
          total: "",
        });
      }
    },
    discountOnchange(ele) {
      console.log("col :", ele);
      var price = ele.price;
      console.log("price is :" + price);
      var discount = ele.discount / 100;
      console.log("discount is :" + discount);

      var main_total = Number(price) - Number(price) * Number(discount);
      console.log("total is :", main_total);
      ele.total = main_total;
    },
    submitBtn() {},
  },
};
</script>

<style>
button {
  border: 2px solid black;
  background: burlywood;
}
.submitEvent {
  margin-left: 492px;
  margin-top: 20px;
}
table,
th,
td {
  border: 1px solid black;
  width: fit-content;
}
.addMorecol {
  margin-left: 471px;
}
</style>
