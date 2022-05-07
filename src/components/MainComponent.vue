 <!-- 
      gender: "Male"
      id: 1
      image: "https://rickandmortyapi.com/api/character/avatar/1.jpeg"
      name: "Rick Sanchez"
      origin: "Earth (C-137)"
      species: "Human"
      status: "Alive"
      type: "Human" 
    -->
<template>
  <section class="container d-flex flex-wrap gap-5 justify-content-center">
    <loader-component v-if="loading" />

    <div class="row">
      <div
        v-for="item in characterList"
        :key="item.id"
        class="col-6 col-md-4 col-lg-3 my-3 text-center"
      >
        <img :src="item.image" :alt="item.name" class="img-fluid" />
        <h4 class="mt-3">{{ item.name }}</h4>
        <div>{{ item.origin }}</div>
        <div class="fw-bold">{{ item.species }}</div>
      </div>
    </div>

    <footer-component v-if="!loading" :len="characterList.length" />
  </section>
</template> 

<script>
import LoaderComponent from "./LoaderComponent.vue";
import FooterComponent from "./FooterComponent.vue";
import axios from "axios";

export default {
  name: "MainComponent",
  components: {
    LoaderComponent,
    FooterComponent,
  },
  data() {
    return {
      characterList: [],
      apiPath: "https://api.sampleapis.com/rickandmorty/",
      loading: false,
    };
  },
  mounted() {
    this.loading = true;
    axios
      .get(this.apiPath + "characters")
      .then((res) => {
        console.log(res);
        this.characterList = [...res.data];
        this.loading = false;
      })
      .catch((error) => {
        console.log(error);
        this.loading = false;
      });
  },
};
</script>

<style lang="scss" scoped>
@import "@/assets/style/variable.scss";

h4 {
  text-transform: uppercase;
  &:after {
    content: "";
    display: block;
    width: 30%;
    height: 2px;
    margin: 1rem auto;
    background: currentColor;
  }
}
img {
  width: 100%;
  border-radius: 50%;
  box-shadow: 0 0 6px 3px rgba(#000, 0.15);
}
</style>

