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
    <div v-for="index in roomCount">
      {{ index }}
      <div class="table_room">
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
    </div>
  </section>
  <section></section>
</template>
<script>
export default {
  name: "App",
  components: {},
  data() {
    return {
      adultRoomCount: 1,
      childRoomCount: 1,
      roomCount: "",
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
    },
    remove_another_room() {
      this.roomCount--;
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
</style>
