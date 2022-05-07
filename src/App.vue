<template>
  <div id="app">
    <header-component :title="titolo" />
    <div>
      <main-component />
    </div>
  </div>
</template>

<script>
import HeaderComponent from "./components/HeaderComponent.vue";
import MainComponent from "./components/MainComponent.vue";

export default {
  name: "App",
  components: {
    HeaderComponent,
    MainComponent,
  },
  data() {
    return {
      titolo: "Rick and Morty",
    };
  },
};
</script>

<style lang="scss">
@import "@/assets/style/general.scss";
</style>
