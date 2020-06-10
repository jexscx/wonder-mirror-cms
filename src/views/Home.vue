<template>
  <div>
    <div id="function-nav">
      <!-- the v-for loop loops through the array we made from the json file. Fr every function it makes a new component-->
      <div
        v-for="func in functionData"
        :key="func.id"
        :to="{ name: 'Filterview', params: { id: func.id } }"
      >
        <div class="function-span">
          <span class="function-name">
            <h2>{{ func.name }}</h2>
          </span>
          <span class="function-active">
            <toggle-button
            :labels="{checked: 'On', unchecked: 'Off'}"
            color="#5756B3"
            :height="30"
            :width="70  "
            v-model="func.active"/>
          </span>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
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

<style scoped>
.function-span{
  padding: 10px 20px;
  margin: 40px;
  display: flex;
  justify-content: space-between;
  align-items: center;
  width: 90vh;
  background: #FFFFFF;
box-shadow: 0px 10px 30px rgba(0, 0, 0, 0.2);
border-radius: 25px;
}
div#functionnav{
  margin: auto;
}
</style>
