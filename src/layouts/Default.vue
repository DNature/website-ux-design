<template>
  <div class="flex flex-col min-h-screen">
    <Nav />
    <div class="flex-1 pt-16">
      <slot />
    </div>
    <Footer />
  </div>
</template>

<static-query>
  query {
    metadata {
      siteName
    }
  }
</static-query>

<script>
import store from "~/store";
import Nav from "~/components/Nav.vue";
import Footer from "~/components/Footer";

export default {
  components: {
    Nav,
    Footer
  },
  computed: {
    currentPage: function() {
      return store.state.currentPage;
    }
  }
};
</script>

<style>
footer {
  /* justify-self: flex-start; */
}
</style>
