<template>
  <div>
    <kanji-header></kanji-header>
    <kanji-search></kanji-search>
  </div>
</template>

<script>
import Header from "./components/header.vue";
import Search from "./components/search.vue";

export default {
  components: {
    "kanji-header": Header,
    "kanji-search": Search
  },
  name: "app",
  data() {
    return {};
  }
};
</script>

<style lang="scss">
</style>
