<template>
  <div class="container">
    <h1 class="text-center">Creative Cards</h1>
    <ul class="nav justify-content-center">
      <li class="nav-item">
        <a class="nav-link" @click="pageSelected='cardFront'">Front</a>
      </li>
      <li class="nav-item">
        <a class="nav-link" @click="pageSelected='cardInsideLeft'">Inside Left</a>
      </li>
      <li class="nav-item">
        <a class="nav-link" @click="pageSelected='cardInsideRight'">Inside Right</a>
      </li>
      <li class="nav-item">
        <a class="nav-link" @click="pageSelected='cardBack'">Back</a>
      </li>
    </ul>
    <hr />
    <ccCardProgress></ccCardProgress>
  </div>
</template>

<script>
import CardProgress from "./card/CardProgress";
export default {
  data() {
    return {
      pageSelected: ""
    };
  },
  watch: {
    pageSelected: function() {
      this.$emit("pageWasChanged", this.pageSelected);
    }
  },
  components: {
    ccCardProgress: CardProgress
  }
};
</script>

<style>
h1 {
  margin-top: 10px;
}
a {
  color: blue !important;
}
</style>