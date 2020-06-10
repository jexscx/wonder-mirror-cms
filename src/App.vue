<template>
  <div id="app" :style="image">
    <TheNavigation />
    <router-view />
  </div>
</template>
<script>
import TheNavigation from "@/components/TheNavigation";
export default {
  components: {
    TheNavigation
  },
    data() {
    return {
      image: { backgroundImage: "url(dashboard/src/assets/backgroundflow.svg)" }
    };
  }
};
</script>
<style>
* {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  box-sizing: border-box;
  padding: 0;
  margin: 0;
}
#app {
  display: grid;
  grid-template-columns: 25% 75%;
  grid-gap: 20px;
    width: 100vw;
  height: 100vh;
  justify-content: center;
  overflow: hidden;
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  color: #2c3e50;
  background-image: url("@assets\backgroundflow.svg");
}

#nav {
  padding: 30px;
  text-align: left;
}

#nav a {
  font-weight: bold;
  color: #2c3e50;
    text-decoration: none;
}
#nav a:hover{
    color: rgb(194, 192, 192);
}

#nav a.router-link-exact-active {
  color: #5756B3;
  text-decoration: none;
}

</style>
