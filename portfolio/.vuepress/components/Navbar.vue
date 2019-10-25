<template>
  <v-toolbar color="white">
    <v-toolbar-title>My Title</v-toolbar-title>
    <v-spacer />
    <v-toolbar-items>
      <v-btn
        v-for="nav in navLinks"
        :key="nav.text"
        :to="nav.link"
        active-class="active"
        v-text="nav.text"
      />
    </v-toolbar-items>
  </v-toolbar>
</template>

<script>
export default {
  props: {
    logo: {
      type: String,
      required: false
    },
    sticky: {
      type: Boolean,
      required: false
    }
  },
  computed: {
    navLinks() {
      return this.$site.themeConfig.nav;
    }
  }
};
</script>
