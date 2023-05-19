<template>
  <section>
    <div>
      <button class="add_another_room" @click="add_another_room">
        Add room
      </button>
    </div>
    <!-- start room div -->
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
    <!-- end room div -->
  </section>
  <hr />
</template>

<script>
export default {
  name: "App",
  components: {},
  data() {
    return {
      rooms: [
        {
          //room_No: 1,
          adult_count: 1,
          child_count: 0,
        },
      ],
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
      let updateStudentList = this.students.filter((el) => el.ele !== ele);
      this.rooms = updateStudentList;
    },
    // remove_another_room() {
    //   // var ele_num = --ele;
    //   // console.log("ele :" + ele_num);
    //   const fruits = this.rooms;
    //   // console.log("fruit array is :" + fruits);
    //   delete fruits[1];

    //   // console.log("ele no :" + ele_num);
    //   // this.rooms.splice(ele_num, 1);
    //   // console.log(this.rooms);
    //   // if (this.rooms.length > 1) {
    //   //   delete this.rooms[2];
    //   // } else {
    //   //   console.log("Else work");
    //   // }
    //   // console.log("add room" + this.roomNo);
    // },
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
button {
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
}
</style>
