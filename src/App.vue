<template>
  <div id="app">
    <HeaderComponent :title="titolo"/>
  </div>
</template>

<script>
import HeaderComponent from './components/HeaderComponent.vue'; 

export default {
  name: 'App',
  components: {
    HeaderComponent
  },
  data(){
    return {
      titolo: "Rick and Morty",
    }
  }
}
</script>

<style lang="scss">
@import "@/assets/style/general.scss";
</style>
