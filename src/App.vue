<template>
  <div className="parent-div">
    <h1>VueJs Training Session</h1>
    <h2>Component</h2>
    <h2>{{ username }}</h2>
    <h2>Email: {{ email }}</h2>
    <button className="click_me" @click="userNameBtn()">Show Username</button>
    <button className="click_me" @click="emailBtn()">Show Email</button>
    <button className="click_me" @click="databaseBtn()">Show Database</button>
    <button className="click_me" @click="passwordBtn()">Show Password</button>
  </div>
</template>

<script>
export default {
  name: "App",
  components: {},
  props: {},
  data() {
    return {
      username: "shyamporiya@123",
      email: "info@vuejs.com ",
      database: "myFirstProject",
      password: ".;dl_kfid",
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
  },
};
</script>

<style scoped>
.click_me {
  color: black;
  background-color: rgb(200, 217, 87);
  border: 4px solid rgb(211, 111, 111);
  font-size: medium;
  font-weight: 300;
}
.click_me:hover {
  color: white;
  background-color: red;
  border: 4px solid goldenrod;
  font-size: 25px;
}
</style>
