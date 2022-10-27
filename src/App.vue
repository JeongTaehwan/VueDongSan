<template>
  <div class="menu">
    <a v-for="(Menu, arr) in menudata" :key="arr">{{ Menu }}</a>
  </div>

  <div class="black-bg" v-if="ModalState == true">
    <div class="white-bg">
      <h4>상세페이지</h4>
      <p>내용</p>
      <button @click="changeModalState()">닫기</button>
    </div>
  </div>

  <!-- <div>
    <h1>원룸샵</h1>
    <div v-for="(Room, arr) in room" :key="arr">
      <h4>{{ Room }} 원룸</h4>
      <p>{{ price[arr] }} 만원</p>
    </div>
    <button @click="changeReportCount()">허위매물신고</button>
    <span>신고수 : {{ ReportCount }}</span>
  </div> -->

  <div>
    <h1>원룸샵</h1>
    <div v-for="(Room, arr) in room" :key="arr">
      <img :src="room[arr].image" class="room_img" />
      <h4 @click="changeModalState()">{{ room[arr]?.title }} 원룸</h4>
      <p>{{ room[arr]?.price }}원</p>
    </div>
  </div>
</template>

<script>
import data from "./assets/post";

export default {
  name: "App",
  data() {
    return {
      room: data,
      menudata: ["Home", "About", "Login"],
      ModalState: false,
    };
  },
  methods: {
    changeModalState() {
      this.ModalState = !this.ModalState;
    },
  },
};
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  padding: 0;
  margin: 0;
}

div {
  box-sizing: border-box;
}

.menu {
  background: darkslateblue;
  padding: 15px;
}

.menu a {
  color: white;
  padding: 10px;
}

.room_img {
  width: 500px;
  height: 300px;
}

.black-bg {
  width: 100%;
  height: 100%;
  background: rgba(0, 0, 0, 0.5);
  position: fixed;
  padding: 20px;
}

.white-bg {
  width: 100%;
  background: white;
  border-radius: 8px;
  padding: 20px;
}
</style>
