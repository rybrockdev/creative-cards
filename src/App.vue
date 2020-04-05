<template>
  <div class="container">
    <div class="row">
      <div class="col-sm-12">
        <nav-header @pageWasChanged="currentPage = $event"></nav-header>
        <keep-alive>
          <component :is="currentPage"></component>
        </keep-alive>
        <cc-footer>
          <p class="text-center" slot="app-name">&copy;{{ appName }}</p>
          <nav>
            <ul class="nav justify-content-center">
              <li class="nav-item">
                <a class="nav-link">home</a>
              </li>
              <li class="nav-item">
                <a class="nav-link">About us</a>
              </li>
              <li class="nav-item">
                <a class="nav-link">contact us</a>
              </li>
            </ul>
          </nav>
        </cc-footer>
      </div>
    </div>
  </div>
</template>

<script>
import firebaseConfig from "../firebaseConfig";
import Header from "./components/Header";
import CardFront from "./components/card/CardFront";
import CardInsideLeft from "./components/card/CardInsideLeft";
import CardInsideRight from "./components/card/CardInsideRight";
import CardBack from "./components/card/CardBack";
import Footer from "./components/Footer";

export default {
  data() {
    return {
      currentPage: "cardFront",
      appName: "Creative Cards"
    };
  },
  components: {
    navHeader: Header,
    cardFront: CardFront,
    cardInsideLeft: CardInsideLeft,
    cardInsideRight: CardInsideRight,
    cardBack: CardBack,
    ccFooter: Footer
  }
};
</script>

<style>
body {
  font-family: Verdana, Geneva, Tahoma, sans-serif;
  color: #333;
}
a {
  cursor: pointer;
}
</style>
