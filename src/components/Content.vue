<template>
  <section>
    <div class="jumbotron"></div>
    <div class="container-fluid">
      <div class="c-series uppercase"><h4>Current series</h4></div>
      <div class="container h-100">
        <Card v-for="(card, index) in cards" :key="index" :card="card" />

        <div class="load-button uppercase"><a href="#">Load more</a></div>
      </div>
    </div>
  </section>
</template>

<script>
import Card from "./ComicsCard.vue";
export default {
  name: "Content",
  components: {
    Card,
  },
  props: ["cards"],
};
</script>

<style lang="scss" scoped>
@import "@/assets/scss/_mixins.scss";
@import "@/assets/scss/_vars.scss";
section {
  div.jumbotron {
    height: 400px;
    background-image: url("../assets/img/jumbotron.jpg");
    background-size: cover;
  }
  div.container-fluid {
    background-color: #1c1c1c;
  }
  .c-series {
    width: 250px;
    padding: 10px 0;
    position: relative;
    bottom: 22px;
    left: 230px;
    background-color: $blue;
    color: #fff;
    text-align: center;
    font-size: 25px;
  }
  div.container {
    background-color: #1c1c1c;
    padding-bottom: 25px;
    @include center("x");
    flex-wrap: wrap;
  }
  .load-button {
    background-color: $blue;
    align-self: center;
    padding: 10px 0;
    &:hover {
      transform: scale(1.1);
    }
    a {
      color: #fff;
      font-weight: bold;
      font-size: 12px;
      padding: 0 50px;
    }
  }
}
</style>