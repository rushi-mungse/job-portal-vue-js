<template>
  <div class="container">
    <Navigation />
    <router-view />
  </div>
</template>

<script>
import Navigation from "./components/Navigation.vue";
export default {
  components: { Navigation },
};
</script>

<style lang="scss" scoped></style>
