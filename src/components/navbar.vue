<template>
  <div>
    <v-app-bar
      color="#00a88f accent-4"
      dense
      dark
      style="padding: 2rem; background: #00a88f; border-radius: 2px"
    >
      <v-toolbar-title style="height: 75px">
        <v-icon>mdi-train</v-icon>

        trainline</v-toolbar-title
      >

      <v-spacer></v-spacer>

      <v-row style="height: 88px">
        <v-col> Basket </v-col>

        <v-col> My Bookings </v-col>

        <v-btn>Sign in</v-btn>
      </v-row>
    </v-app-bar>
  </div>
</template>

<script>
export default {
  name: "NavbarComponent",
  data() {
    return {};
  },
};
</script>

<style scoped>
.v-toolbar__content {
  height: 10px;
}
</style>
