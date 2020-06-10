<template>
  <div>
    <b-card-group deck>
            <b-card
        :img-src="require(`@/assets/logo.png`)"
        style="max-width: 20rem;"
      >
        <b-card-text>
          Make a new filter
        </b-card-text>
        <b-button variant="primary"> + </b-button>
      </b-card>
      <!-- loop through the filters of the fuction and make a cardfor every filter found -->
      <b-card
      
        v-for="filter in getCurrentFunction.filters"
        :key="filter.name"
        :img-src="require(`@/assets/${filter.image}`)"
        :img-alt="filter.name"
        style="max-width: 20rem;"
      >
        <b-card-text>
          {{ filter.name }}
        </b-card-text>
        <b-button variant="primary"> </b-button>
      </b-card>
    </b-card-group>
  </div>
</template>
<script>
export default {
  data() {
    return {
      functionData: null,
      funcId: this.$route.params.id,
    };
  },
  created() {
    fetch("functionData.json")
      .then((response) => response.json())
      .then((functionData) => {
        this.functionData = functionData;
      });
  },
  computed: {
    getCurrentFunction() {
      if (this.functionData !== null) {
        return this.functionData.find((item) => item.id === this.funcId);
      }
      return null;
    },
  },
};
</script>
