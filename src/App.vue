<template>
  <div class="menu">
    <a v-for="(Menu, arr) in menudata" :key="arr">{{ Menu }}</a>
  </div>

  <div>
    <h1>원룸샵</h1>
    <div v-for="(Room, arr) in room" :key="arr">
      <h4>{{ Room }} 원룸</h4>
      <p>{{ price[arr] }} 만원</p>
    </div>
  </div>
</template>

<script>
export default {
  name: "App",
  data() {
    return {
      room: ["준하우스", "비닐하우스"],
      price: [50, 100],
      menudata: ["Home", "About", "Login"],
    };
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
}

.menu {
  background: darkslateblue;
  padding: 15px;
  border-radius: 5px;
}

.menu a {
  color: white;
  padding: 10px;
}
</style>
