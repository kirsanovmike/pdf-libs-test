<template>
  <section class="pb-8" id="contact">
    <div class="svg-border-waves text-white">
      <v-img src="~@/assets/img/borderWavesBlue.svg" />
    </div>
    <v-snackbar
      v-model="snackbar.enabled"
      timeout="3000"
      right
      top
      :color="snackbar.color"
    >
      {{ snackbar.text }}

      <template v-slot:action="{ attrs }">
        <v-btn text v-bind="attrs" @click="snackbar.enabled = false">
          Fechar
        </v-btn>
      </template>
    </v-snackbar>
  </section>
</template>

<style scoped>
#contact {
  background-color: #f4f7f5;
}

.svg-border-waves .v-image {
  position: absolute;
  bottom: 0;
  left: 0;
  height: 3rem;
  width: 100%;
  overflow: hidden;
}
</style>

<script>
// import {db} from '@/main'

export default {
  data: () => ({
    icons: ["fa-facebook", "fa-twitter", "fa-linkedin", "fa-instagram"],
    valid: true,
    name: "",
    nameRules: [(v) => !!v || "Name is required"],
    email: "",
    emailRules: [(v) => !!v || "Email is required"],
    textArea: "",
    textAreaRules: [(v) => !!v || "Message is required"],
    lazy: false,
    snackbar: {
      enabled: false,
      text: "",
      color: "",
    },
  }),
  methods: {
    submit() {},
  },
};
</script>
