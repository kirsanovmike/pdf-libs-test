<template>
  <v-container fluid class="pa-0">
    <privacy-policy />
  </v-container>
</template>

<style scoped>
.v-main {
  background-image: url("~@/assets/img/bgMain.png");
  background-attachment: fixed;
  background-position: center;
  background-size: cover;
}
</style>

<script>
import PrivacyPolicy from "@/components/PrivacyPolicy.vue";

export default {
  name: "App",
  components: {
    PrivacyPolicy,
  },
};
</script>
