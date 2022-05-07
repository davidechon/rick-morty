<template>
  <header>
    <h1 class="text-center my-3">{{ title }}</h1>
  </header>
</template>

<script>
export default {
  name: "HeaderComponent",
  props: ["title"],
};
</script>


<style lang="scss" scoped>
header {
  h1 {
    font-weight: 700;
  }
}
</style>