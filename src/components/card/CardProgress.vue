<template>
  <div class="row">
    <div class="col-sm-12">
      <p>
        completed
        <span id="counter">0</span> /4:
      </p>
      <progress value="0" max="100" id="cardProgress">0%</progress>
    </div>
  </div>
</template>

<script>
import { EventBus } from "../../main";

export default {
  data() {
    return {};
  },
  created() {
    EventBus.$on("markAsCompleted", function(data) {
      if (data) {
        document.getElementById("counter").innerText++;
        document.getElementById("cardProgress").value += 25;
      } else {
        document.getElementById("counter").innerText - 1;
        document.getElementById("cardProgress").value -= 25;
      }
    });
  }
};
</script>

<style scoped>
progress {
  width: 100%;
}
</style>