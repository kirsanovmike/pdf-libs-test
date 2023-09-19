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
import foote from "@/components/Footer";
import PrivacyPolicy from "@/components/PrivacyPolicy.vue";

export default {
  name: "App",

  components: {
    navigation,
    foote,
    PrivacyPolicy,
  },

  data: () => ({
    fab: null,
    color: "",
    flat: null,
  }),

  computed: {
    noDocument() {
      return (
        this.$route.query.document === "" || this.$route.query.document == null
      );
    },
    showPrivacy() {
      return this.$route.query.document === "privacy-policy";
    },
    showTerms() {
      return this.$route.query.document === "terms-of-use";
    },
  },

  created() {
    const top = window.pageYOffset || 0;
    if (top <= 60) {
      this.color = "transparent";
      this.flat = true;
    }
  },

  watch: {
    fab(value) {
      if (value) {
        this.color = "secondary";
        this.flat = false;
      } else {
        this.color = "transparent";
        this.flat = true;
      }
    },
  },

  methods: {
    onScroll(e) {
      if (typeof window === "undefined") return;
      const top = window.pageYOffset || e.target.scrollTop || 0;
      this.fab = top > 60;
    },
    toTop() {
      this.$vuetify.goTo(0);
    },
  },
};
</script>
