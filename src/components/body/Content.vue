<template>
  <!-- <section>
    <div>
      <button class="add_another_room" @click="add_another_room">
        Add room
      </button>
    </div>
    
   <div class="table_room" v-for="(elem, index) in rooms" :key="index">
      <span class="room-name">Room - {{ ++index }}</span>
      <div class="adult">
        <span class="adultName">Adult</span>
        <div class="add_div">
          <button style="margin-left: 10px" @click="decBtnAdult(elem)">
            -
          </button>
          <input
            type="text"
            style="margin-left: 5px; width: 20px"
            v-model="elem.adult_count"
          />
          <button style="margin-left: 5px" @click="incBtnAdult(elem)">+</button>
        </div>
      </div>

      <div class="child_Div">
        <span class="adultName">Child</span>
        <div class="add_div_new">
          <button style="margin-left: 10px" @click="decBtnChild(elem)">
            -
          </button>
          <input
            type="text"
            style="margin-left: 5px; width: 20px"
            v-model="elem.child_count"
          />
          <button style="margin-left: 5px" @click="incBtnChild(elem)">+</button>
        </div>
      </div>
      <div class="removeRoom">
        <button class="remove_room" @click="remove_another_room()">
          Remove room
        </button>
      </div>
    </div>
    
  </section> -->

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
              id="product_name"
            />
          </td>

          <td>
            <select
              style="border: 2px solid black; width: 100px"
              id="category_name"
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
              id="price_val"
            />
          </td>
          <td>
            <input
              style="width: 100px"
              type="text"
              placeholder="Discount %"
              id="dis_val"
              @input="discountOnchange()"
            />
          </td>
          <td>
            <input
              style="width: 60px"
              type="text"
              placeholder="Total"
              disabled
              id="total_val"
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
    <div class="parent-div">
      <table style="width: 30%">
        <tr>
          <th>Product Name</th>
          <th>Category</th>
          <th>Price</th>
          <th>Discount</th>
          <th>Total</th>
        </tr>
        <tr v-for="(col, index) in getList" :key="index">
          <td>
            <input v-model="col.productName" readonly="true" />
          </td>
          <td>
            <input v-model="col.categoryName" readonly="true" />
          </td>
          <td>
            <input v-model="col.price" readonly="true" />
          </td>
          <td>
            <input v-model="col.discount" readonly="true" />
          </td>
          <td>
            <input v-model="col.total" readonly="true" />
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
      getList: [],
    };
  },
  methods: {
    add_another_room() {
      console.log("value room :" + this.room_val);
      this.rooms.push({
        adult_count: 1,
        child_count: 0,
      });
      // console.log("add room" + this.roomNo);
    },
    remove_another_room(ele) {
      // remove_another_room() {
      var ele_num = --ele;
      console.log("room no is:" + ele_num);
      if (this.rooms.length > 1) {
        this.rooms.splice(ele_num, 1);
      }
    },

    incBtnAdult(obj) {
      console.log("click+");
      obj.adult_count++;
    },
    decBtnAdult(obj) {
      if (obj.adult_count !== 1) {
        obj.adult_count--;
      }
    },
    incBtnChild(obj) {
      obj.child_count++;
    },
    decBtnChild(obj) {
      if (obj.child_count !== 0) {
        obj.child_count--;
      }
    },
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
    submitBtn() {
      console.log("hell");
      // var listData = this.productData.map((index, val, arr) => {
      //   return index.product;
      //   console.log("index" + index);
      //if (this.productList.length > 1) {
      this.productList.forEach((value, index) => {
        //arr.push(value);
        console.log(value);
        console.log(index);

        this.getList.push({
          productName: document.getElementById("product_name").value,
          categoryName: document.getElementById("category_name").value,
          price: document.getElementById("price_val").value,
          discount: document.getElementById("dis_val").value,
          total: document.getElementById("total_val").value,
        });
      });

      /*foreach(productList as key => value){
          this.getList.push({
            productName: "qwe",
            categoryName: "qwe",
            price: "zczxxz",
            discount: "asd",
            total: "asd",
          });
        }*/
      //}
    },
  },
  product_name_0() {
    console.log("hello");
  },
};
</script>

<script></script>
<style>
/* .add_div {
  margin-left: -4px;
  margin-top: 6px;
}
.add_child_div {
  margin-left: 175px;
  margin-top: -60px;
} */
/* .adultName {
  font-size: 22px;
  font-weight: 700;
  font-family: fangsong;
  /* border: 2px solid black; */
/*} */
/* .childName {
  padding: 3px 5px 0px 5px;
  font-size: 22px;
  font-weight: 700;
  font-family: fangsong;
  border: 2px solid black;
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
} */

/* this page new css */
/* button {
  border: 2px solid black;
  background: burlywood;
}

.room-name {
  padding: 0px 7px 5px 10px;
  margin-left: 100px;
  font-size: 22px;
  font-weight: 700;
  font-family: fangsong;
  border: 2px solid black;
}

.add_another_room {
  margin-left: 223px;
  margin-top: 10px;
  margin-bottom: 2px;
}
.table_room {
  border: 2px solid black;
  margin-left: 13px;
  height: 140px;
  width: 290px;
  background-color: aliceblue;
  width: 300px;
  height: 180px;
}
.adult {
  padding: 0px 12px 4px 12px;
  margin-left: 9px;
  margin-right: 42px;
  margin-top: 12px;
  border: 1px solid grey;
  width: 120px;
}
.adultName {
  font-size: 22px;
  font-weight: 700;
  font-family: fangsong;
  margin-left: 14px;
}
.child_Div {
  border: 1px solid grey;
  width: 110px;
  margin-top: -69px;
  margin-left: 160px;
  padding: 0px 2px 3px 10px;
}
.removeRoom {
  margin-left: 176px;
  margin-top: 30px;
}
.remove_room {
  background: #a0e0e3;
} */

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
