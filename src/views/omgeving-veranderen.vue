<template>
  <div>
    <div>
      <div>
        Refresh the page!
        <video ref="video" id="video" width="150" height="120" autoplay></video>
      </div>
      <canvas id="c1" width="400" height="372"></canvas>

      <change-background></change-background>
    </div>
  </div>
</template>

<script>
import ChangeBackground from "@/components/component-change-background.vue";
export default {
  components: {
    ChangeBackground,
  },
  data() {
    return {};
  },
};
</script>
<style lang="scss" scoped>
p {
  font-size: 12px;
}
#video {
  display: none;
}
#c1 {
  display: none;
}
#c2 {
  background-repeat: no-repeat;
  background-size: 330px;
  height: auto;
}
</style>
