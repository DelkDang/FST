<template>
  <v-app>
    <v-container bg fill-height grid-list-md text-xs-center>
      <v-layout row wrap align-center>
        <v-flex>
          <div class="text-h3 my-4 text-center font-weight-bold">Welcome</div>
          <CopyTextField />
        </v-flex>
      </v-layout>
    </v-container>
  </v-app>
</template>

<script>
export default {
  name: "IndexPage",
  computed: {
    theme() {
      return (this.$vuetify.theme.dark) ? "dark" : "light";
    }
  },

}
</script>
