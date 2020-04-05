<template>
  <div class="row">
    <div class="form-check form-check-inline">
      <div class="form-check-label">
        <input type="checkbox" class="form-check-input" v-model="check" @click="sectionCompleted" />mark section as complete
      </div>
    </div>
  </div>
</template>

<script>
import { EventBus } from "../../main";
export default {
  data() {
    return {
      check: ""
    };
  },
  methods: {
    sectionCompleted: function() {
      EventBus.$emit("markAsCompleted", this.check);
    }
  }
};
</script>

<style>
</style>