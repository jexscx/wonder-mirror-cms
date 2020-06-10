<template>
  <div>
    <FunctionNavigation />
    <router-view />
  </div>
</template>
<script>
import FunctionNavigation from "@/components/FunctionNavigation";
export default {
  components: {
    FunctionNavigation
  }
};
</script>
