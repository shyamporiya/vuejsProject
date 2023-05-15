<template>
  <div className="parent-div">
    <h1>VueJs Training Session</h1>
    <h2>Component</h2>
    <h2>{{ username }}</h2>
    <h2>Email: {{ email }}</h2>
    <h2>Address : {{ address }}</h2>
    <!-- <p>List{{ list }}</p> -->
    <span>List Of (Using fetch details):{{ listingData }}</span>
    <button className="click_me" @click="userNameBtn()">Show Username</button>
    <button className="" @click="emailBtn()">Show Email</button>
    <button className="" @click="databaseBtn()">Show Database</button>
    <button className="" @click="passwordBtn()">Show Password</button>
    <button className="" @click="fetchBtn()">Fetch Address</button>
    <button className="" @click="fetchListBtn()">Fetch List</button>
  </div>
</template>

<script>
export default {
  name: "Structure",
  components: {},
  props: {},
  data() {
    return {
      username: "shyamporiya@123",
      email: "info@vuejs.com ",
      database: "myFirstProject",
      password: ".;dl_kfid",
      address: "",
      listingData: [],
      list: [
        { city: "ahmedabad", state: "gujarat" },
        { city: "mumbai", state: "maharashtra" },
        { city: "hyderabad", state: "telangana" },
        { city: "chennai", state: "tamilnadu" },
        { city: "jaipur", state: "rajasthan" },
      ],
      ifexample: true,
      showExample: true,
    };
  },
  methods: {
    userNameBtn() {
      const name = this.username;
      console.log("From username :", name);
      alert("UserName is : " + name);
    },
    emailBtn() {
      const email = this.email;
      console.log("Your Email Is : " + email);
      alert("Your Email is : " + email);
    },
    databaseBtn() {
      const databaseName = this.database;
      console.log("From Database : " + databaseName);
      alert("Your Database is : " + databaseName);
    },
    passwordBtn() {
      const password = this.password;
      console.log("From Password : " + password);
      console.log("test: " + password);
      alert("Your Password is : " + password);
    },
    fetchBtn() {
      console.log("hello");
      this.address = "Ahmedabad Navrangpura";
    },
    fetchListBtn() {
      const listarray = this.list.map((key, index, arr) => {
        return key.city;
        // console.log("key : ", key);
        // console.log("index : ", index);
        // console.log("arr : ", arr);
      });
      console.log("list : ", listarray);
      this.listingData = listarray;
    },
  },
};
</script>

<style scoped>
.click_me {
  color: rgb(224, 238, 240);
  background-color: navy;
  border: 2px solid white;
  font-size: medium;
  font-weight: 500;
}
.click_me:hover {
  color: white;
  background-color: red;
  border: 4px solid goldenrod;
  font-size: 25px;
}
</style>
