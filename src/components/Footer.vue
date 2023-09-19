<template>
  <v-footer dark padless>
    <v-card flat tile class="secondary white--text text-center">
      <!-- <v-card-text>
        <v-btn
          v-for="(icon, i) in icons"
          :key="i"
          class="mx-4 white--text"
          :href="icon.link"
          target="_blank"
          icon
        >
          <v-icon size="24px">{{ icon.text }}</v-icon>
        </v-btn>
      </v-card-text> -->

      <v-card-text class="white--text pt-0">
        Thank you for being with us. We try to make the best services for you.
      </v-card-text>

      <v-divider></v-divider>

      <v-card-text class="white--text">
        {{ new Date().getFullYear() }} — <strong>pdf-libs-test</strong>
      </v-card-text>

      <v-divider></v-divider>

      <v-card-text class="white--text">
        <v-btn class="ma-2" outlined color="white" @click="openPrivacyPolicy">
          Docment
        </v-btn>
      </v-card-text>
    </v-card>
  </v-footer>
</template>

<style scoped>
.v-card {
  width: 100%;
}
</style>

<script>
export default {
  methods: {
    openPrivacyPolicy() {
      window
        .open(
          `${
            process.env.NODE_ENV === "production" ? "/pdf-libs-test/" : "/"
          }?document=privacy-policy`,
          "_blank"
        )
        .focus();
    },
  },
};
</script>
