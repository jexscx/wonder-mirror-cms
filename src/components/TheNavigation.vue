<template>
  <div id="nav">
    <h1>Wonder mirror</h1>
    <router-link :to="{ name: 'Home' }">
      <span>
        <!-- <Home /> -->
      </span>
      <span>
        <h2>Home</h2>
      </span>
    </router-link>
    <router-link :to="{ name: 'Settings' }">
      <span>
        <!-- <Settings /> -->
      </span>
      <span>
        <h2>Settings</h2>
      </span>
    </router-link>
        <router-link :to="{ name: 'Background filter' }">
      <span>
        <!-- <home /> -->
      </span>
      <span>
        <h2>Background Filter</h2>
      </span>
    </router-link>
  </div>
</template>
<script>
import Home from "vue-material-design-icons/Home.vue";
import Settings from "vue-material-design-icons/SettingsHelper.vue";
export default {
  Home,
  Settings
};
</script>
<style scoped>
#nav{
background: #FFFFFF;
box-shadow: 10px 0px 40px rgba(0, 0, 0, 0.2);
border-radius: 0px 25px 25px 0px;
display: block;
}
h2 {
  font-size: 25px;
}
</style>
