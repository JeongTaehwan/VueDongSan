<template>
  <div class="menu">
    <a v-for="Menu in menudata" :key="Menu">{{ Menu }}</a>
  </div>

  <div>
    원룸샵
    <h4>{{ room[0] }} 원룸</h4>
    <p>{{ price[0] }} 만원</p>
  </div>
  <div>
    <h4>{{ room[1] }} 원룸</h4>
    <p>{{ price[1] }} 만원</p>
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
  margin-top: 60px;
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
