<template>
  <div id="app">
    <h1>ค้นหาเพลงที่คุณชอบบบบ</h1>
    <iTune />
  </div>
</template>
<script>
import iTune from "./components/iTune.vue";
export default {
  name: "App",
  components: {
    iTune
  },
};
</script>
<style>
#app {
  font-family: "Pridi", serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #9abeff;
  margin-top: 60px;
}
body{
  background-image: url('https://media.discordapp.net/attachments/402366472665432064/761102031716089856/4695fdc211ce2e5adff27b5b242d4e3f.jpg?width=528&height=396');
  background-attachment: fixed;
  background-position: center;
  background-repeat: no-repeat;
  background-size: cover;
}
</style>