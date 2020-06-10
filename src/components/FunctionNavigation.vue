<template>
  <div>
    <div id="function-nav">
      <!-- the v-for loop loops through the array we made from the json file. For every function it makes a new component-->
      <router-link
        v-for="func in functionData"
        :key="func.id"
        :to="{ name: 'Filterview', params: { id: func.id } }"
      >
        <div class="function-span">
          <span class="function-name">
            <h2>{{ func.name }}</h2>
          </span>
          <span class="number-active-filters">
            <p>{{ func.activefilters }} filter(s) active</p>
          </span>
          <span class="function-arrow">
            <chevron-right />
          </span>
        </div>
      </router-link>
    </div>
  </div>
</template>
<script>
import ChevronRight from "vue-material-design-icons/ChevronRight.vue";

export default {
  components: {
    ChevronRight,
  },
  data() {
    return {
      functionData: null,
    };
  },
  created() {
    fetch("functionData.json")
      .then((response) => response.json())
      .then((functionData) => {
        this.functionData = functionData;
      });
  },
};
</script>

<style lang="css" scoped>
#function-nav {
  padding: 40px 0px;
  display: grid;
  gap: 40px;
  width: 90%;
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
}
.function-span {
  display: grid;
  grid-template-columns: 33% 33% 33%;
  padding: 10px 20px;
  background: #ffffff;
  box-shadow: 10px 0px 40px rgba(0, 0, 0, 0.2);
  border-radius: 25px 25px 25px 25px;
}
.function-span:hover{
  background: rgb(238, 238, 255);
}
.function-name {
  display: flex;
  justify-content: flex-start;
  align-items: center;
  text-align: left;
    color: #2c3e50;
  text-decoration: none;
}
.number-active-filters {
     display: flex;
      justify-content: center;
  align-items: center;
    color: #00C2FF;
  text-decoration: none;

  
}
.function-arrow {
     display: flex;
      justify-content: flex-end;
  align-items: center;
    color: #2c3e50;
  text-decoration: none;

}
:hover{
  text-decoration: none;
}
.material-design-icon > .material-design-icon__svg {
  size: 48px;
}
</style>
